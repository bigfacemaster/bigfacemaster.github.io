---
title: EChartsForReact
date: 2021-01-16 19:21:17
tags: [ARTS, Share, React, ECharts, React-for-ECharts]
category: [ARTS, Tools]
---

# 封装[ECharts Next For React](https://www.npmjs.com/package/echarts-next-for-react)

> 起因是因为想用[ECharts Next (v5) 版本](https://echarts.apache.org/next/zh/tutorial.html), 而[echarts-for-react](https://github.com/hustcc/echarts-for-react)目前支持到**v4**，查看了一下其源码，决定自己封装一下，来完成业务开发。

## 源码

```tsx
import type { FC } from 'react';
import React, { useEffect, useRef } from 'react';
import type { EChartsOption } from 'echarts';
import { dispose, getInstanceByDom, init } from 'echarts';
import classNames from 'classnames';
import isFunction from 'lodash/isFunction';
import isEmpty from 'lodash/isEmpty';
import isString from 'lodash/isString';
import { bind, clear } from 'size-sensor';
import { useMount, useUnmount } from 'react-use';
import 'echarts-gl';

export type EChartsNextForReactCoreProps = {
  option: EChartsOption;
  notMerge?: boolean;
  replaceMerge?: string | string[];
  lazyUpdate?: boolean;
  silent?: boolean;
  style?: React.CSSProperties;
  className?: string;
  theme?: string | Record<string, unknown>;
  opts?: {
    renderer?: 'canvas' | 'svg';
    devicePixelRatio?: number;
    width?: number;
    height?: number;
    locale?: string | any;
  };
  showLoading?: boolean;
  onChartReady?: (arg0: any) => void;
  onEvents?: Record<string, unknown>;
};

const EChartsNextForReactCore: FC<EChartsNextForReactCoreProps> = (props) => {
  const {
    style,
    className,
    theme,
    opts,
    option,
    notMerge,
    lazyUpdate,
    showLoading,
    onChartReady,
    onEvents,
  } = props;
  const chartRefElements = useRef<HTMLDivElement>(null);

  const getChartInstance = () => {
    if (chartRefElements?.current) {
      return (
        getInstanceByDom(chartRefElements?.current) ?? init(chartRefElements?.current, theme, opts)
      );
    }
    return undefined;
  };

  const getChartDom = () => {
    const chartObj = getChartInstance();
    if (chartObj) {
      chartObj.setOption(option, notMerge ?? false, !!lazyUpdate ?? false);
      if (showLoading) {
        chartObj.showLoading();
      } else {
        chartObj.hideLoading();
      }
      return chartObj;
    }
    return undefined;
  };

  const bindEvents = () => {
    const chartElms = getChartDom();
    if (!isEmpty(onEvents) && chartElms) {
      // @ts-ignore
      // eslint-disable-next-line no-restricted-syntax
      for (const [key, func] of Object.entries(onEvents)) {
        if (
          Object.prototype.hasOwnProperty.call(onEvents, key) &&
          isString(key) &&
          isFunction(func)
        ) {
          chartElms.on(key, (param: any) => {
            func(param, chartElms);
          });
        }
      }
    }
  };

  const renderChart = () => {
    const chartObj = getChartDom();
    bindEvents();
    if (chartObj) {
      if (isFunction(onChartReady)) {
        onChartReady(chartObj);
      } else if (chartRefElements) {
        bind(chartRefElements?.current, () => {
          try {
            chartObj?.resize();
          } catch (e) {
            console.error(e);
          }
        });
      }
    }
  };

  const disposeCurrentChart = () => {
    if (chartRefElements?.current) {
      clear(chartRefElements?.current);
      dispose(chartRefElements?.current);
    }
  };

  useMount(() => {
    renderChart();
  });

  useEffect(() => {
    disposeCurrentChart();
    renderChart();
  }, [theme, opts, onEvents]);

  useEffect(() => {
    const chartDom = getChartDom();
    // @ts-ignore
    if (chartDom?._dom) {
      // @ts-ignore
      bind(chartDom._dom, () => {
        try {
          chartDom?.resize();
        } catch (e) {
          console.error(e);
        }
      });
    }
  }, [style, className, showLoading]);

  useUnmount(() => {
    disposeCurrentChart();
  });

  return (
    <div
      ref={chartRefElements}
      style={{
        height: 360,
        ...style,
      }}
      className={classNames('echarts-next-for-react', className)}
    />
  );
};

EChartsNextForReactCore.defaultProps = {
  notMerge: false,
  lazyUpdate: false,
  showLoading: false,
};

export default EChartsNextForReactCore;

```

## 使用

```sh
npm install echarts-next-for-react -s

yarn add echarts-next-for-react
```



## 封装过程中遇到的问题

在最初的一版时，能够正常显示，加入了**lazyUpdate**属性之后，发现**Chart**直接崩掉，报错。

经过排查发现是因为，**bind dom**事件时，直接使用了

```tsx
const chartRefElements = useRef<HTMLDivElement>(null);
```

返回的对象，而不是其真实的**dom**对象

```tsx
  useEffect(() => {
    const chartDom = getChartDom();
    if (chartDom) {
      chartDom.resize();
    }
  }, [style, className, showLoading]);
```

改成了

```tsx
  useEffect(() => {
    const chartDom = getChartDom();
    if (chartDom?._dom) {
      bind(chartDom._dom, () => {
        try {
          chartDom?.resize();
        } catch (e) {
          console.error(e);
        }
      });
    }
  }, [style, className, showLoading]);
```

这样之后，就可以完整运行了，并且可以实现事件的绑定等操作。



> 总结：在使用开源软件的时候，与其在等别人开发不如积极主动的参与。
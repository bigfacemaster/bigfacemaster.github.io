---
title: ECharts graph 类型的图表绘制
date: 2021-01-29 14:33:19
tags: - ECharts

---



# ECharts graph 类型的图表绘制

由于最近项目中需要绘制树形图，其展示形式大致如下：

<img src="http://bigfacemaster.test.upcdn.net/uPic/image-20210129143654597.png" alt="image-20210129143654597" style="zoom:50%;" />

在项目中，目前定义的图表全部使用的是[React + echarts-next-for-react](https://www.npmjs.com/package/echarts-next-for-react)，根据查看[Echarts](https://echarts.apache.org/) Demo 查看基本的树类型，大致都只能绘制成如下：<img src="http://bigfacemaster.test.upcdn.net/uPic/image-20210129144431878.png" alt="image-20210129144431878" style="zoom: 33%;" />

经过查看文档发现类型为**graph**能够满足需求。

在这个类型的**series**中重点有三个参数**nodes、links、categoris**，其类型都是数组。

>nodes主要是来显示各个点的名称、位置、*id*等其他信息

> links主要用来连接各个点: **{ soure: ‘0’, target: ‘1’ }[]**

> categories主要就是用来对点的分类了。

````tsx
const basicSpace = 300;
const xAxisStart = -2000;
const yAxisStart = 400;
const symbolSize = 50;

export default {
  nodes: [
    {
      id: '0',
      name: null,
      symbolSize: 0,
      x: xAxisStart,
      y: yAxisStart,
      category: 0,
    },
    {
      id: '1',
      name: null,
      symbol: `image://${imgURL}`,
      symbolSize,
      x: xAxisStart,
      y: yAxisStart + basicSpace,
      category: 0,
    },
    {
      id: '2',
      name: null,
      symbolSize: 0,
      x: xAxisStart,
      y: yAxisStart + basicSpace * 2,
      category: 0,
    },

    {
      id: '3',
      name: null,
      symbol: `image://${imgURL}`,
      symbolSize: 36,
      x: xAxisStart + basicSpace,
      y: yAxisStart,
      category: 0,
    },
    {
      id: '4',
      name: null,
      symbol: `image://${imgURL}`,
      symbolSize: 36,
      x: xAxisStart + basicSpace,
      y: yAxisStart + basicSpace,
      category: 0,
    },
    {
      id: '5',
      name: null,
      symbol: `image://${imgURL}`,
      symbolSize: 36,
      x: xAxisStart + basicSpace,
      y: yAxisStart + basicSpace * 2,
      category: 0,
    },

    {
      id: '6',
      name: null,
      symbolSize: 0,
      x: xAxisStart + basicSpace * 2,
      y: yAxisStart,
      category: 0,
    },
    {
      id: '7',
      name: null,
      symbolSize: 0,
      x: xAxisStart + basicSpace * 2,
      y: yAxisStart + basicSpace,
      value: 4,
      category: 0,
    },
    {
      id: '8',
      name: null,
      symbolSize: 0,
      x: xAxisStart + basicSpace * 2,
      y: yAxisStart + basicSpace * 2,
      category: 0,
    },
    {
      id: '9',
      name: 'Center',
      symbol: `image://${imgURL}`,
      symbolSize,
      label: {
        position: 'bottom',
      },
      x: xAxisStart + basicSpace * 3,
      y: yAxisStart + basicSpace,
      category: 0,
    },
    {
      id: '10',
      name: null,
      symbolSize: 0,
      x: xAxisStart + basicSpace * 4,
      y: yAxisStart + basicSpace,
      value: 4,
      category: 0,
    },

    {
      id: '11',
      name: 'Node',
      symbolSize: 0,
      x: xAxisStart + basicSpace * 3,
      y: yAxisStart + basicSpace * 6,
      category: 0,
    },
    {
      id: '12',
      name: null,
      symbolSize: 0,
      x: xAxisStart + basicSpace * 4,
      y: yAxisStart + basicSpace * 6,
      category: 0,
    },

    {
      id: '13',
      name: 'Node 1',
      symbolSize: 0,
      x: xAxisStart + basicSpace * 3,
      y: yAxisStart + basicSpace * 9,
      category: 0,
    },

    {
      id: '14',
      name: null,
      symbolSize: 0,
      label: {
        position: 'bottom',
      },
      x: xAxisStart + basicSpace * 4,
      y: yAxisStart + basicSpace * 9,
      category: 0,
    },
  ],
  links: [
    {
      source: '0',
      target: '1',
    },
    {
      source: '2',
      target: '1',
    },
    {
      source: '3',
      target: '0',
    },
    {
      source: '4',
      target: '1',
    },
    {
      source: '5',
      target: '2',
    },
    {
      source: '6',
      target: '3',
    },
    {
      source: '6',
      target: '7',
    },
    {
      source: '8',
      target: '7',
    },
    {
      source: '7',
      target: '4',
    },
    {
      source: '8',
      target: '5',
    },
    {
      source: '9',
      target: '7',
    },
    {
      source: '10',
      target: '9',
    },
    {
      source: '11',
      target: '9',
    },
    {
      source: '12',
      target: '11',
    },
    {
      source: '13',
      target: '11',
    },
    {
      source: '14',
      target: '13',
    },
  ],
  categories: [
    {
      name: 'internet',
    },
  ],
};

````

这个就是前面*0~15*个节点的基本关系，而后的是根据不同的数据来便利生成的，主要是规则就是，先生成空节点，并且link到目的点，然后再生成带图的点，再link到上一个点，如此循环，就可以大致满足需求了。

![image-20210129145425028](http://bigfacemaster.test.upcdn.net/uPic/image-20210129145425028.png)
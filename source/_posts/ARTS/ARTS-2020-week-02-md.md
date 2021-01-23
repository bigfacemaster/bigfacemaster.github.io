---
title: ARTS-2020-week-02.md
date: 2021-01-03 17:56:22
tags:
    - ARTS
    - Algorithm
    - Review
    - Tip
    - Share
    - 算法
    - 阅读
    - 技巧
    - 分享
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

# [杨辉三角](https://leetcode-cn.com/problems/pascals-triangle/)

给定一个非负整数 *numRows，*生成杨辉三角的前 *numRows* 行。

```js
const triangle = (pre, line) => {
  const result = [];
  const param = pre[pre.length - 1];
  
  for (i = 0; i < param.length + 1; i++) {
    const first = Number(param[i - 1] || 0);
    const send = Number(param[i] || 0);
    result.push(first + send); 
  }
  
  return result;
}

const generater = (numRows) => {
  const result = [];
  for (i = 1; i < numRows + 1; i++) {
    if (i === 1) {
      result.push([1]);
    } else if (i === 2) {
      result.push([1, 1]);
    } else if (i > 2){
      result.push(triangle(result, i));
    }
  }
  return result;
}
```





# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

[Top 5 In-Demand JavaScript Frameworks for Front-End Development in 2020](https://medium.com/javascript-in-plain-english/top-5-in-demand-javascript-frameworks-for-front-end-development-in-2020-a59c4340d082)

在以前使用过**angular**，做过简单开发，后续公司技术栈全部切换到**react**，现在也是使用**react**最新17，react越来越强大，还是有不少问题，但是在稳健发展，尤其是近期更新的**hooks**,**suspense**,以及未来的 **react server component**都是一个从 **web、 mobile、desktop、back-end**不断发展的。同时国内有强大的**react**组件**ant -design**及其生态链**ant-design + umijs**能够进行快速的业务开发，**umi**团队也提供了完整的**微前端**方案：qiankun。框架大体上都是相通的，所以主要还是取决于公司技术栈、业务发展等因素。

# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

> useRef

该**API**属于**react hooks**

**useRef**返回一个可变的**ref**对象。

最初的**.current**是在进行初始化的时候传入的值。返回的**ref**对象在组件的的整个生命周期内保持不变。

**useRef**可在**.current**中保存一个可变的盒子，用来保存可变值，**useRef**创建的是一个普通的**js**对象，同时在每一次渲染时回返回同一个**ref**对象。

如果需要**ref**变化时，来做一些操作。可回调函数来做监控(useCallBack)。

```tsx
const refDemo = () => {
  const inputEl = useRef<HTMLInputElement>(null);
  
  return <input ref={inputEl} type="text"/>
}
```



```jsx
const MeasureExample = () => {
  const [height, setHeight] = useState(0);

  const measuredRef = useCallback(node => {
    if (node !== null) {
      setHeight(node.getBoundingClientRect().height);
    }
  }, []);

  return (
    <>
      <h1 ref={measuredRef}>Hello, world</h1>
      <h2>The above header is {Math.round(height)}px tall</h2>
    </>
  );
}
```



# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

[git merge vs rebase](https://bigfacemaster.cn/2021/01/09/Tools/gitMergeVsRebase/)




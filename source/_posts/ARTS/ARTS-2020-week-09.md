---
title: ARTS-2020-week-09
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
date: 2021-02-21 20:30:40
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

#### 程序员面试宝典 [面试题 01.01. 判定字符是否唯一](https://leetcode-cn.com/problems/is-unique-lcci/)

实现一个算法，确定一个字符串 `s` 的所有字符是否全都不同。

```js
var isUnique = function(astr) {
  if(astr && astr.length > 26) {
    return false;
  } else {
    const uniqArr = Array.from(new Set(astr.split('')));
    return uniqArr.length === astr.length;
  }
};
```



# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

[JavaScript performance beyond bundle size](https://nolanlawson.com/2021/02/23/javascript-performance-beyond-bundle-size/)

三个问题：how big are your dependencies? Could you use a smaller one? Could you lazy-load it?

关键因数 

- Parse/compile time
- Execution time
- Power usage
- Memory usage
- Disk usage

使用*webpack bundle analyzer*/ rollup plugin analyzer 等分析工具以及Chrome 控制栏的各种工具来完成分析优化工作。


# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

在使用**dependencies/devDependencies**要考虑依赖包之间的依赖包的兼容性，比如项目使用的是**react v16.8**而所需要的组件包是**react v17**那么就是需要作包兼容性处理**”react”: “~16.8”**

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

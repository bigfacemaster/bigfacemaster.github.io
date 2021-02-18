---
title: ARTS-2020-week-08
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
date: 2021-02-17 21:51:10
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

## [剑指 Offer 17. 打印从1到最大的n位数](https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/)

输入数字 `n`，按顺序打印出从 1 到最大的 n 位十进制数。比如输入 3，则打印出 1、2、3 一直到最大的 3 位数 999。

```javascript
const printNumbers = function(n) {
  const last = Math.pow(10, n);
  const res = [];
  for(let i = 1; i < last; i++) {
    res.push(i);
  }
  return res;
};
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文


# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

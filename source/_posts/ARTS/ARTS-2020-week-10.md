---
title: ARTS-2020-week-10
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
date: 2021-02-27 13:14:11
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

## [剑指 Offer 21. 调整数组顺序使奇数位于偶数前面](https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/)

输入一个整数数组，实现一个函数来调整该数组中数字的顺序，使得所有奇数位于数组的前半部分，所有偶数位于数组的后半部分。



```js
const exchange = function(nums) {
  const odds = nums.filter(v => v % 2 === 1);
  const evens = nums.filter(v => v % 2 === 0);
  return [...odds, ...evens];
};
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文


# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观


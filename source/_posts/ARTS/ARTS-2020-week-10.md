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

[Why is esbuild fast?](https://esbuild.github.io/faq/#why-is-esbuild-fast)

原因:

> * 使用Go语言编写，而不是js(It's written in [Go](https://golang.org/) and compiles to native code.)：go 并行处理任务，js单线程。go线程共享内存，js线程序列化。垃圾回收机制，go堆栈共享，js单独回收。
> * 大量使用并行(Parallelism is used heavily.)：充分使用cpu资源
> * 一切从头编写(Everything in esbuild is written from scratch.)：不依赖于第三方库，可以从头设计并考虑性能。
> * 内存使用效率(Memory is used efficiently.)：最大时间复杂度：O(n);充分利用CPU和内存。

构建速度快；

# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观


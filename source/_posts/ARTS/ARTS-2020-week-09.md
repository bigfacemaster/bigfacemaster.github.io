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

[ES modules: A cartoon deep-dive](https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/)


# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

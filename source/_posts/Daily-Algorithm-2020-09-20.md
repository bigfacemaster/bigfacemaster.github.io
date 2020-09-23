---
title: Daily-Algorithm-2020-09-20
date: 2020-09-20 19:44:35
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [转置矩阵](https://leetcode-cn.com/problems/transpose-matrix/)

## Desc

给定一个矩阵 `A`， 返回 `A` 的转置矩阵。

矩阵的转置是指将矩阵的主对角线翻转，交换矩阵的行索引与列索引。



## Code

```js

var transpose = function(A) {
  return Array.from({ length: A[0].length }, (_v, i) => A.map(v =>v [i]));
};
```


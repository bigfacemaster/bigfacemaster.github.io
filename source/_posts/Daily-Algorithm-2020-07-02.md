---
title: Daily-Algorithm-2020-07-02
date: 2020-07-02 09:07:22
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [有序矩阵中第K小的元素](https://leetcode-cn.com/problems/kth-smallest-element-in-a-sorted-matrix/)

## Desc

给定一个 *`n x n`* 矩阵，其中每行和每列元素均按升序排序，找到矩阵中第 `k` 小的元素。
请注意，它是排序后的第 `k` 小元素，而不是第 `k` 个不同的元素。

## Code

```js
var kthSmallest = function(matrix, k) {
  return matrix.flat().sort((a, b) => a - b)[k - 1];
};
```


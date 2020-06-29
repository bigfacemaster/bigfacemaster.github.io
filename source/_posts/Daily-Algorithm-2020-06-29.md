---
title: Daily-Algorithm-2020-06-29
date: 2020-06-29 09:24:28
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [数组中的第K个最大元素](https://leetcode-cn.com/problems/kth-largest-element-in-an-array/)

## Desc

在未排序的数组中找到第 **k** 个最大的元素。请注意，你需要找的是数组排序后的第 k 个最大的元素，而不是第 k 个不同的元素。

## Code

```js
var findKthLargest = function(nums, k) {
  return nums.sort((a,b) => a - b).reverse()[k-1];
};
```


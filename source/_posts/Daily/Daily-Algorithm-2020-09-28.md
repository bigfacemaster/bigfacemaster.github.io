---
title: Daily-Algorithm-2020-09-28
date: 2020-09-28 09:28:14
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [有序数组中出现次数超过25%的元素](https://leetcode-cn.com/problems/element-appearing-more-than-25-in-sorted-array/)

## Desc

给你一个非递减的 **有序** 整数数组，已知这个数组中恰好有一个整数，它的出现次数超过数组元素总数的 25%。

请你找到并返回这个整数



## Code

```js
var findSpecialInteger = function(arr) {
  return arr.length<2 ? arr[0] : arr.filter(n => ((arr.lastIndexOf(n) - arr.indexOf(n)+1) / (arr.length+1) >= 0.25))[0];
};
```


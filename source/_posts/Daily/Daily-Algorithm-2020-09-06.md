---
title: Daily-Algorithm-2020-09-06
date: 2020-09-06 17:22:15
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [三个数的最大乘积](https://leetcode-cn.com/problems/maximum-product-of-three-numbers/)

## Desc

给定一个整型数组，在数组中找出由三个数组成的最大乘积，并输出这个乘积。



## Code

```js
var maximumProduct = function(nums) {
  const sorted = nums.sort((a,b) => a - b);
  const lng = sorted.length;
  const last = sorted[lng - 1];
  const temp1 = sorted[lng - 3] * sorted[lng - 2];
  const temp2 = sorted[0] * sorted[1]
  return Math.max(temp1, temp2) * last;
};
```


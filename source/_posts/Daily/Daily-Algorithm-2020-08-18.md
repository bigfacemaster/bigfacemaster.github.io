---
title: Daily-Algorithm-2020-08-18
date: 2020-08-18 09:45:42
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [最大子序和](https://leetcode-cn.com/problems/maximum-subarray/)

## Desc

给定一个整数数组 `nums` ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。

## Code

```js
var maxSubArray = function(nums) {
  let pre = 0;
  let max = nums[0];
  nums.forEach((x) => {
    pre = Math.max(pre + x, x);
    max = Math.max(max, pre);
  });
  return max;
};
```


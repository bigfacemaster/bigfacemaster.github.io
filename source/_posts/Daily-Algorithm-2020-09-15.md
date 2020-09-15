---
title: Daily-Algorithm-2020-09-15
date: 2020-09-15 10:17:44
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [第 k 个缺失的正整数](https://leetcode-cn.com/problems/kth-missing-positive-number/)

## Desc

给你一个 **严格升序排列** 的正整数数组 `arr` 和一个整数 `k` 。

请你找到这个数组里第 `k` 个缺失的正整数。



## Code

```js
var findKthPositive = function(arr, k) {
  let result = 1;
  while (k > 0) {
    if(arr.indexOf(result) == -1) {
      k--;
    }
    if(k != 0) {
      result++;
    }
  }
  return result;
};
```


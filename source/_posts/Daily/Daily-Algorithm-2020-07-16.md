---
title: Daily-Algorithm-2020-07-16
date: 2020-07-16 10:06:55
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

#  [子数组最大平均数 I](https://leetcode-cn.com/problems/maximum-average-subarray-i/)

## Desc

给定 `n` 个整数，找出平均数最大且长度为 `k` 的连续子数组，并输出该最大平均数。



## Code

```js
var findMaxAverage = function(nums, k) {
  let result = -Infinity;
  for(let i = k - 1; i < nums.length; i++) {

    const sum = summer(nums.slice(i - k + 1, i + 1));
    
    result = Math.max(result, sum/k);
    
  }
  return result;
};

const summer = arr => {
  let result = 0;
  for(let v of arr) {
    result += v;
  }
  return result;
}
```


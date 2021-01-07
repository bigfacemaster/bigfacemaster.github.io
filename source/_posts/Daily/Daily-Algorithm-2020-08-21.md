---
title: Daily-Algorithm-2020-08-21
date: 2020-08-21 09:36:26
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [存在连续三个奇数的数组](https://leetcode-cn.com/problems/three-consecutive-odds/)

## Desc

给你一个整数数组 `arr`，请你判断数组中是否存在连续三个元素都是奇数的情况：如果存在，请返回 `true` ；否则，返回 `false` 。

 

## Code

```js
var threeConsecutiveOdds = function(arr) {
  if(arr.length < 3) {
    return false;
  }
  let result = false;
  for(let i = 2; i < arr.length; i++) {
    if(isOdd(arr[i - 2]) && isOdd(arr[i - 1]) && isOdd(arr[i])) {
      return true;
    }
  }
  return result;
};

const isOdd = v => v % 2 === 1;
```


---
title: Daily-Algorithm-2020-07-13
date: 2020-07-13 09:22:08
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [判断能否形成等差数列](https://leetcode-cn.com/problems/can-make-arithmetic-progression-from-sequence/)

## Desc


给你一个数字数组 `arr` 。

如果一个数列中，任意相邻两项的差总等于同一个常数，那么这个数列就称为 **等差数列** 。

如果可以重新排列数组形成等差数列，请返回 `true` ；否则，返回 `false` 。



## Code

```js
var canMakeArithmeticProgression = function(arr) {
  const sortedArr = arr.sort((a, b) => a - b );
  const difference = sortedArr[1] - sortedArr[0];
  let result = true;

  for (let i = 1; i < sortedArr.length; i++) {
    const differ = sortedArr[i] - sortedArr[i-1];
    if(differ !== difference) {
      result = false;
      return false;
    }
  }
  return result;
};
```


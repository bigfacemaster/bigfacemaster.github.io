---
title: Daily-Algorithm-2020-07-31
date: 2020-07-31 09:43:51
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [按奇偶排序数组](https://leetcode-cn.com/problems/sort-array-by-parity/)

## Desc



给定一个非负整数数组 `A`，返回一个数组，在该数组中， `A` 的所有偶数元素之后跟着所有奇数元素。

你可以返回满足此条件的任何数组作为答案。



## Code

```js
var sortArrayByParity = function(A) {
  const evens = [];
  const odds = []
  A.forEach(v => {
    if(v % 2 === 0) {
      evens.push(v);
    } else {
      odds.push(v);
    }
  });
  return [...evens, ...odds];
};
```


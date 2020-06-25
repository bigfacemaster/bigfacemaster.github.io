---
title: Daily-Algorithm-2020-06-25
date: 2020-06-25 21:23:26
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [2的幂](https://leetcode-cn.com/problems/power-of-two/)

## Desc

给定一个整数，编写一个函数来判断它是否是 2 的幂次方。

## Code

```js
var isPowerOfTwo = function(n) {
  if(n !== 0) {
    const result = Math.log2(n);
    return Math.ceil(result) === result;
  } 
  return false;
};
```


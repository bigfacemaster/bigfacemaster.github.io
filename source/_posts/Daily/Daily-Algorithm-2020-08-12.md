---
title: Daily-Algorithm-2020-08-12
date: 2020-08-12 09:21:14
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [平方数之和](https://leetcode-cn.com/problems/sum-of-square-numbers/)

## Desc

给定一个非负整数 `c` ，你要判断是否存在两个整数 `a` 和 `b`，使得 a2 + b2 = c。



## Code

```js
var judgeSquareSum = function(c) {
  for(let i = 0; i * i <= c; i++) {
    let other = Math.sqrt(c - i * i);
    if( other % 1 === 0) {
      return true;
    }
  }
  return false;
};
```


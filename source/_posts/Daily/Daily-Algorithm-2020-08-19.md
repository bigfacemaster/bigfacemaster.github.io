---
title: Daily-Algorithm-2020-08-19
date: 2020-08-19 09:50:31
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [颠倒二进制位](https://leetcode-cn.com/problems/reverse-bits/)

## Desc

颠倒给定的 32 位无符号整数的二进制位。



## Code

```js
var reverseBits = function(n) {
    const str = n.toString(2);
    const num = '0'.repeat(32 - str.length) + str;
    return parseInt(num.split('').reduce((total, str) => str + total, ''), 2);
};
```


---
title: Daily-Algorithm-2020-08-23
date: 2020-08-23 20:13:50
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [丑数](https://leetcode-cn.com/problems/ugly-number/)

## Desc

编写一个程序判断给定的数是否为丑数。

丑数就是只包含质因数 `2, 3, 5` 的**正整数**。



## Code

```js
var isUgly = function(num) {
  if(num === 0) {
    return false;
  } if(num === 1) {
    return true;
  } else if(num % 2 === 0) {
    return isUgly(num / 2);
  } else if(num % 3 === 0) {
    return isUgly(num / 3);
  } else if(num % 5 === 0) {
    return isUgly(num / 5);
  } else {
    return false;
  }
};
```


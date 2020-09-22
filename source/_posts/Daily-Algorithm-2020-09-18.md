---
title: Daily-Algorithm-2020-09-18
date: 2020-09-18 09:09:23
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [阶乘后的零](https://leetcode-cn.com/problems/factorial-trailing-zeroes/)

## Desc

给定一个整数 *n*，返回 *n*! 结果尾数中零的数量。



## Code

```js
var trailingZeroes = function(n) {
  let result = 0;
  while(n >= 5){
    result += n / 5 | 0;
    n /= 5;
  }
  return result;

};
```


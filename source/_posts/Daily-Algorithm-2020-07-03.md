---
title: Daily-Algorithm-2020-07-03
date: 2020-07-03 10:01:41
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [七进制数](https://leetcode-cn.com/problems/base-7/)

## Desc

给定一个整数，将其转化为7进制，并以字符串形式输出。

## Code

```js
var convertToBase7 = function(num) {
  if( num >= 0) {
    return num.toString(7);
  }

  return `-${ Math.abs(num).toString(7) }`;
};
```

> JS偷懒大法
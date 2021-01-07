---
title: Daily-Algorithm-2020-07-08
date: 2020-07-08 09:37:50
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [各位相加](https://leetcode-cn.com/problems/add-digits/)

## Desc

给定一个非负整数 `num`，反复将各个位上的数字相加，直到结果为一位数。

## Code

```js
var addDigits = function(num) {
  if(num < 9) {
    return num
  }
  return num % 9 || 9;
};
```


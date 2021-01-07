---
title: Daily-Algorithm-2020-08-26
date: 2020-08-26 09:21:46
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [在区间范围内统计奇数数目](https://leetcode-cn.com/problems/count-odd-numbers-in-an-interval-range/)

## Desc

给你两个非负整数 `low` 和 `high` 。请你返回 `low` 和 `high` 之间（包括二者）奇数的数目。



## Code

```js
var countOdds = function(low, high) {
  let result = 0;
  for(let i = low; i <= high; i++) {
    if(isOdd(i)) {
      result += 1;
    }
  }
  return result;
};

const isOdd = v => v % 2 === 1;


```


---
title: Daily-Algorithm-2020-07-23
date: 2020-07-23 09:24:11
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

## [将数字变成 0 的操作次数](https://leetcode-cn.com/problems/number-of-steps-to-reduce-a-number-to-zero/)

## Desc

给你一个非负整数 `num` ，请你返回将它变成 0 所需要的步数。 如果当前数字是偶数，你需要把它除以 2 ；否则，减去 1 。



## Code

```js
var numberOfSteps  = function(num) {
  let times = 0;
  let value = num;
  while(value > 0) {
    times += 1;
    if(isEven(value)) {
      value = value / 2;
    } else {
      value -= 1;
    }
  }
  return times;
};

const isEven = n => n % 2 === 0 ;
```


---
title: Daily-Algorithm-2020-06-13
date: 2020-06-14 10:47:40
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---



#  [整数反转](https://leetcode-cn.com/problems/reverse-integer/)



## Desc 

给出一个 32 位的有符号整数，你需要将这个整数中每位上的数字进行反转。

注意:

假设我们的环境只能存储得下 32 位的有符号整数，则其数值范围为 [−231,  231 − 1]。请根据这个假设，如果反转后整数溢出那么就返回 0。



## Code



```js
var reverse = function(x) {
  let result = 0;
  if (-Math.pow(2, 31)  <= x && x <= (Math.pow(2, 31) - 1) ) {
    if(x >= 0) {
      result = Number((x).toString().split('').reverse().join(''));
    } else {
      result = -Number((-x).toString().split('').reverse().join(''));
    }
  } else {
    result = 0;
  }
  if( -Math.pow(2, 31)  <= result && result <= (Math.pow(2, 31) - 1)) {
    return result;
  } else  {
    return 0;
  }
};

```


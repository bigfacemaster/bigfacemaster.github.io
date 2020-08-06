---
title: Daily-Algorithm-2020-08-06
date: 2020-08-06 10:07:05
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [整数的各位积和之差](https://leetcode-cn.com/problems/subtract-the-product-and-sum-of-digits-of-an-integer/)

## Desc

给你一个整数 `n`，请你帮忙计算并返回该整数「各位数字之积」与「各位数字之和」的差。



## Code

```js
var subtractProductAndSum = function(n) {
  const arr = String(n).split('');
  let product = 1;
  let sum = 0;
  console.log(arr)
  for(let v of arr) {

    product *= Number(v);
    sum += Number(v);
  }

  return product - sum;
};
```


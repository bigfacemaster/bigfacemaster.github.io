---
title: Daily-Algorithm-2020-06-24
date: 2020-06-24 09:52:44
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [统计位数为偶数的数字](https://leetcode-cn.com/problems/find-numbers-with-even-number-of-digits/)

## Desc

给你一个整数数组 `nums`，请你返回其中位数为 **偶数** 的数字的个数。

## Code

```js
const findNumbers = function(nums) {
  let total = 0;
  nums.forEach(v => {
    const str = `${v}`;
    if(str.length % 2 === 0) {
      total += 1;
    }
  })
  return total;
};
```


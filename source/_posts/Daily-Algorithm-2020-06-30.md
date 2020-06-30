---
title: Daily-Algorithm-2020-06-30
date: 2020-06-30 20:30:36
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [缺失数字](https://leetcode-cn.com/problems/missing-number/)

## Desc

给定一个包含 `0, 1, 2, ..., n` 中 *n* 个数的序列，找出 0 .. *n* 中没有出现在序列中的那个数。

## Code

```js
var missingNumber = function(nums) {
  const numsNew = nums.sort( (a, b) => a - b );
  for(let i = 0; i < numsNew.length; i++) {
    if(i !== numsNew[i]) {
      return i;
    }
  }

  return nums.length;
};
```


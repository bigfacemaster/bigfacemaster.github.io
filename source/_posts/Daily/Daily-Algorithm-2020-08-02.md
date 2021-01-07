---
title: Daily-Algorithm-2020-08-02
date: 2020-08-02 11:52:33
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [第三大的数](https://leetcode-cn.com/problems/third-maximum-number/)

## Desc

给定一个非空数组，返回此数组中第三大的数。如果不存在，则返回数组中最大的数。要求算法时间复杂度必须是O(n)。



## Code

```js
var thirdMax = function(nums) {
  const set = new Set(nums);

  const newNums = [...set].sort((a, b) => a - b);
  const lng = newNums.length;
  if(lng < 3) {
    return newNums[lng - 1];
  }
  return newNums[lng - 3]
};
```


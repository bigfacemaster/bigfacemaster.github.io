---
title: Daily-Algorithm-2020-08-22
date: 2020-08-22 12:46:06
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [存在重复元素](https://leetcode-cn.com/problems/contains-duplicate/)

## Desc

给定一个整数数组，判断是否存在重复元素。

如果任意一值在数组中出现至少两次，函数返回 `true` 。如果数组中每个元素都不相同，则返回 `false` 。



## Code

```js
var containsDuplicate = function(nums) {
  if(nums.length === 0 || nums.length === 1)  {
    return false;
  }
  return nums.length !== Array.from(new Set(nums)).length;
};
```


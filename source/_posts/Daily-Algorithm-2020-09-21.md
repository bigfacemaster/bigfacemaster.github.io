---
title: Daily-Algorithm-2020-09-21
date: 2020-09-21 09:21:17
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [移动零](https://leetcode-cn.com/problems/move-zeroes/)

## Desc

给定一个数组 `nums`，编写一个函数将所有 `0` 移动到数组的末尾，同时保持非零元素的相对顺序。



## Code

```js
var moveZeroes = function(nums) {
  return nums.sort((a,b) => b ? 0 : -1);
};
```


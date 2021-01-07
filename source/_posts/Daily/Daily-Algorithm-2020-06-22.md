---
title: Daily-Algorithm-2020-06-22
date: 2020-06-22 09:16:02
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [旋转数组](https://leetcode-cn.com/problems/rotate-array/)



## Desc

给定一个数组，将数组中的元素向右移动 *k* 个位置，其中 *k* 是非负数。



## Code



```js
const rotate = (nums, k) => nums.splice(0,0,...nums.splice(nums.length-k))
```


---
title: Daily-Algorithm-2020-06-27
date: 2020-06-27 15:38:51
tags: [Algorithm, 算法]
category: [Algorithm, 算法
---

# [两个数组的交集](https://leetcode-cn.com/problems/intersection-of-two-arrays/)

## Desc

给定两个数组，编写一个函数来计算它们的交集。

## Code

```js
const intersection = function(nums1, nums2) {
  if (nums1.length > nums2.length) {
    return intersect(nums1, nums2);
  }
  return intersect(nums2, nums1);
};

const intersect = (long, short) => {
  const result = [];
  short.forEach(v => {
    const temp = long.find(i => i === v);
    if(temp || temp === 0) {
      result.push(temp);
    }
  })
  return [...new Set(result)];
}
```


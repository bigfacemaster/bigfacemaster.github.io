---
title: Daily-Algorithm-2020-07-26
date: 2020-07-26 18:48:02
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [统计有序矩阵中的负数](https://leetcode-cn.com/problems/count-negative-numbers-in-a-sorted-matrix/)

## Desc

给你一个 `m * n` 的矩阵 `grid`，矩阵中的元素无论是按行还是按列，都以非递增顺序排列。 

请你统计并返回 `grid` 中 **负数** 的数目。



## Code

```js
var countNegatives = function(grid) {
  let result = 0;
  for(let g of grid) {
    g.forEach( v => {
      if(v < 0) {
        result += 1;
      }
    })
  }
  return result;
};
```


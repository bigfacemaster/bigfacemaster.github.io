---
title: Daily-Algorithm-2020-09-17
date: 2020-09-17 10:01:58
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [矩阵对角线元素的和](https://leetcode-cn.com/problems/matrix-diagonal-sum/)

## Desc

给你一个正方形矩阵 `mat`，请你返回矩阵对角线元素的和。

请你返回在矩阵主对角线上的元素和副对角线上且不在主对角线上元素的和。



## Code

```js

var diagonalSum = function(mat) {
  if(mat.length === 1) {
    return mat[0][0];
  }
  return mat.reduce((count, v, i) => {
    if(i === (v.length - 1 - i)) {
      return count + v[i];
    }
    return count + (v[i] + v[v.length - 1 - i]);
  }, 0);
};
```


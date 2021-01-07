---
title: Daily-Algorithm-2020-08-15
date: 2020-08-15 22:43:14
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [托普利茨矩阵](https://leetcode-cn.com/problems/toeplitz-matrix/)

## Desc

如果矩阵上每一条由左上到右下的对角线上的元素都相同，那么这个矩阵是 托普利茨矩阵 。

给定一个 M x N 的矩阵，当且仅当它是托普利茨矩阵时返回 True。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/toeplitz-matrix
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var isToeplitzMatrix = function(matrix) {
  if (matrix.length === 1 || matrix[0].length === 1) {
    return true;
  }
  for (let i =1 ;i < matrix.length; i++) {
    for (let j = 1;j < matrix[0].length; j++) {
        if (matrix[i][j] !== matrix[i-1][j-1]) {
            return false;
        }
    }
  }
  return true;
};
```


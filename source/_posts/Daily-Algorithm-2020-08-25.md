---
title: Daily-Algorithm-2020-08-25
date: 2020-08-25 09:12:26
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [ 矩阵中的幸运数](https://leetcode-cn.com/problems/lucky-numbers-in-a-matrix/)

## Desc

给你一个 m * n 的矩阵，矩阵中的数字 各不相同 。请你按 任意 顺序返回矩阵中的所有幸运数。

幸运数是指矩阵中满足同时下列两个条件的元素：

在同一行的所有元素中最小
在同一列的所有元素中最大

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/lucky-numbers-in-a-matrix
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var luckyNumbers  = function(matrix) {
  const mins = matrix.map(row => Math.min(...row));
  const maxs = matrix[0].map((item,col_index) => Math.max(...matrix.map(row => row[col_index])));
    return maxs.filter(item => mins.includes(item));
};	
```


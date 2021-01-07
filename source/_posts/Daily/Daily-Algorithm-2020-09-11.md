---
title: Daily-Algorithm-2020-09-11
date: 2020-09-11 09:23:24
tags:tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

## Desc

给你一个 n 行 m 列的矩阵，最开始的时候，每个单元格中的值都是 0。

另有一个索引数组 indices，indices[i] = [ri, ci] 中的 ri 和 ci 分别表示指定的行和列（从 0 开始编号）。

你需要将每对 [ri, ci] 指定的行和列上的所有单元格的值加 1。

请你在执行完所有 indices 指定的增量操作后，返回矩阵中 「奇数值单元格」 的数目。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/cells-with-odd-values-in-a-matrix
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

## Code

```js
var oddCells = function(n, m, indices) {
  let arr = Array.apply(null, Array(n)).map(t => Array(m).fill(0))

  for(let n of indices){
    let [i, j] = n
    arr[i] = arr[i].map(t => ++t)
    arr.forEach(r => r[j]++) 
  }

  let res = 0
  for(let item of arr){
    res += item.filter(t => t % 2 === 1).length
  }
  return res;
};
```


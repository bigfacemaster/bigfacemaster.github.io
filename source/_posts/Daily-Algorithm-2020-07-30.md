---
title: Daily-Algorithm-2020-07-30
date: 2020-07-30 09:24:44
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [K 次取反后最大化的数组和](https://leetcode-cn.com/problems/maximize-sum-of-array-after-k-negations/)

## Desc

给定一个整数数组 A，我们只能用以下方法修改该数组：我们选择某个索引 i 并将 A[i] 替换为 -A[i]，然后总共重复这个过程 K 次。（我们可以多次选择同一个索引 i。）

以这种方式修改数组后，返回数组可能的最大和。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/maximize-sum-of-array-after-k-negations
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var largestSumAfterKNegations = function(A, K) {
  // for(let i = 0; i < K; i++) {
  //   const index = A.findIndex(v => v === Math.min(...A));
  //   A[index] = A[index] * (-1);
  // }
  // let result = 0;
  // A.forEach(v => result += v);
  // return result;
  let sorted = A.sort((a, b) => a - b);
  for(let i = 0; i < K; i++) {
    sorted[0] = sorted[0] * (-1);
    sorted = sorted.sort((a, b) => a - b);
  }
  let result = 0;
  sorted.forEach(v => result += v);
  return result;
};
```


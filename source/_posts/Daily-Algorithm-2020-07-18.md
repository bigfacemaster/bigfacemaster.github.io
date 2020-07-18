---
title: Daily-Algorithm-2020-07-18
date: 2020-07-18 21:39:50
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [第 N 个泰波那契数](https://leetcode-cn.com/problems/n-th-tribonacci-number/)

## Desc

泰波那契序列 Tn 定义如下： 

T0 = 0, T1 = 1, T2 = 1, 且在 n >= 0 的条件下 Tn+3 = Tn + Tn+1 + Tn+2

给你整数 n，请返回第 n 个泰波那契数 Tn 的值。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/n-th-tribonacci-number
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var tribonacci = function(n) {
  if( n === 0) {
    return 0;
  } else if( n === 1 || n === 2) {
    return 1;
  } else {
    return tribonacci(n - 1) + tribonacci(n - 2) + tribonacci(n - 3);
  }
};
```


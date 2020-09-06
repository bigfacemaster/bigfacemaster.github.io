---
title: Daily-Algorithm-2020-09-05
date: 2020-09-05 21:08:11
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [数字的补数](https://leetcode-cn.com/problems/number-complement/)

## Desc

给定一个正整数，输出它的补数。补数是对该数的二进制表示取反。



## Code

```js
var findComplement = function(num) {
return parseInt(num.toString(2).replace(/0/g, '2').replace(/1/g, '0').replace(/2/g, '1'), 2);
};
```


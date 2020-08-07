---
title: Daily-Algorithm-2020-08-07
date: 2020-08-07 09:16:18
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [6 和 9 组成的最大数字](https://leetcode-cn.com/problems/maximum-69-number/)

## Desc

给你一个仅由数字 6 和 9 组成的正整数 `num`。

你最多只能翻转一位数字，将 6 变成 9，或者把 9 变成 6 。

请返回你可以得到的最大数字。



## Code

```js
var maximum69Number  = function(num) {
    return +(num+'').replace("6", "9")
};
```


---
title: Daily-Algorithm-2020-06-23
date: 2020-06-23 09:13:51
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

#[二进制求和](https://leetcode-cn.com/problems/add-binary/)



## Desc

给你两个二进制字符串，返回它们的和（用二进制表示）。

输入为 **非空** 字符串且只包含数字 `1` 和 `0`。

```js
const addBinary = function(a, b) {
    const intA = BigInt(`0b${a}`, 2);
    const intB = BigInt(`0b${b}`, 2);
    const result = intA + intB;

    return result.toString(2);
};
```


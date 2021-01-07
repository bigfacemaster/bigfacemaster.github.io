---
title: Daily-Algorithm-2020-06-28
date: 2020-06-28 09:22:39
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [ 位1的个数](https://leetcode-cn.com/problems/number-of-1-bits/)

## Desc

编写一个函数，输入是一个无符号整数，返回其二进制表达式中数字位数为 ‘1’ 的个数（也被称为[汉明重量](https://baike.baidu.com/item/汉明重量)）。

## Code

```js
const hammingWeight = function(n) {
    const bit = n.toString(2).split('');
    let result = 0;
    for( let i = 0; i < bit.length; i ++ ) {
      if (Number(bit[i]) === 1) {
        result += 1;
      }
    }
    return result;
};
```


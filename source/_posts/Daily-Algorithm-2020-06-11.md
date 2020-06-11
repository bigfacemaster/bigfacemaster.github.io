---
title: Daily-Algorithm-2020-06-11
date: 2020-06-11 11:04:43
tags: Algorithm, 算法
category: Algorithm, 算法
---



# [罗马数字转整数](https://leetcode-cn.com/problems/roman-to-integer/)

## Desc

罗马数字包含以下七种字符: `I`， `V`， `X`， `L`，`C`，`D` 和 `M`。

字符          数值
I             1
V             5
X             10
L             50
C             100
D             500
M             1000

通常情况下，罗马数字中小的数字在大的数字的右边。但也存在特例，例如 4 不写做 IIII，而是 IV。数字 1 在数字 5 的左边，所表示的数等于大数 5 减小数 1 得到的数值 4 。同样地，数字 9 表示为 IX。这个特殊的规则只适用于以下六种情况：

I 可以放在 V (5) 和 X (10) 的左边，来表示 4 和 9。
X 可以放在 L (50) 和 C (100) 的左边，来表示 40 和 90。 
C 可以放在 D (500) 和 M (1000) 的左边，来表示 400 和 900。
给定一个罗马数字，将其转换成整数。输入确保在 1 到 3999 的范围内。



## 题解(JS)



```js
const romanToInt = s => {
  const roman = {
    I: 1,
    V: 5,
    X: 10,
    L: 50,
    C: 100,
    D: 500,
    M: 1000,
  };
  let result = 0;
  const sArr = s.split('');
  sArr.forEach((v, k )=> {
    if(k > 0) {
      if(roman[v] <= roman[sArr[k-1]]) {
        result += roman[v];
      } else {
        result -= roman[sArr[k-1]];
        result += (roman[v] - roman[sArr[k-1]])
      }
    } else {
      result += roman[v];
    }
  });
  return result;
};

romanToInt("III") // 3
romanToInt("IX")  // 9
```








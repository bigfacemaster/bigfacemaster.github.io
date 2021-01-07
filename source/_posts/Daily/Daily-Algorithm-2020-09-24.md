---
title: Daily-Algorithm-2020-09-24
date: 2020-09-24 09:51:53
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [连续字符](https://leetcode-cn.com/problems/consecutive-characters/)

## Desc

给你一个字符串 `s` ，字符串的「能量」定义为：只包含一种字符的最长非空子字符串的长度。

请你返回字符串的能量。



## Code

```js
var maxPower = function(s) {
  return s.match(/(\w)\1*/g).sort((a,b)=>b.length-a.length)[0].length;
};
```


---
title: Daily-Algorithm-2020-08-10
date: 2020-08-10 09:55:44
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [找不同](https://leetcode-cn.com/problems/find-the-difference/)

## Desc

给定两个字符串 ***s*** 和 ***t***，它们只包含小写字母。

字符串 ***t\*** 由字符串 ***s\*** 随机重排，然后在随机位置添加一个字母。

请找出在 ***t*** 中被添加的字母。



## Code

```js
var findTheDifference = function(s, t) {
  for(let item of s){
    t = t.replace(item, '')
  }
  return t;
};
```


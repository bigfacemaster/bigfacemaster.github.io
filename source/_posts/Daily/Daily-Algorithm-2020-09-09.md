---
title: Daily-Algorithm-2020-09-09
date: 2020-09-09 09:50:02
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

#  [千位分隔数](https://leetcode-cn.com/problems/thousand-separator/)

## Desc

给你一个整数 `n`，请你每隔三位添加点（即 "." 符号）作为千位分隔符，并将结果以字符串格式返回。



## Code

```js
var thousandSeparator = function(n) {
  return n.toLocaleString().replace(/,/g, '.');
};
```


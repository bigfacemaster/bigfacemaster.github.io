---
title: Daily-Algorithm-2020-08-27
date: 2020-08-27 09:11:58
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [日期之间隔几天](https://leetcode-cn.com/problems/number-of-days-between-two-dates/)

## Desc

请你编写一个程序来计算两个日期之间隔了多少天。

日期以字符串形式给出，格式为 `YYYY-MM-DD`，如示例所示。



## Code

```js
var daysBetweenDates = function(date1, date2) {
  const standard = 24 * 60 * 60 * 1000;
  const differ = Math.abs( (new Date(date1).valueOf()) - (new Date(date2).valueOf()) );
  return differ / standard;
};
```


---
title: Daily-Algorithm-2020-07-04
date: 2020-07-04 17:32:20
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [一年中的第几天](https://leetcode-cn.com/problems/day-of-the-year/)

## Desc

给你一个按 YYYY-MM-DD 格式表示日期的字符串 date，请你计算并返回该日期是当年的第几天。

通常情况下，我们认为 1 月 1 日是每年的第 1 天，1 月 2 日是每年的第 2 天，依此类推。每个月的天数与现行公元纪年法（格里高利历）一致。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/day-of-the-year
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

## Code

```js
const dayOfYear = function(date) {
  const dateArr = date.split('-');
  const isLeap = new Date(dateArr[0], 2,0).getDate() === 29;
  const days = [
     0,
     31,
     isLeap ? 29 : 28,
     31,
     30,
     31,
     30,
     31,
     31,
     30,
     31,
     30
  ];
  let result = Number(dateArr[2]);
  for(let i = 0; i < Number(dateArr[1]); i++) {
    result += days[i];
  }
  return result;
};
```


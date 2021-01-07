---
title: Daily-Algorithm-2020-07-12
date: 2020-07-12 21:03:15
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [转变日期格式](https://leetcode-cn.com/problems/reformat-date/)

## Desc

给你一个字符串 date ，它的格式为 Day Month Year ，其中：

Day 是集合 {"1st", "2nd", "3rd", "4th", ..., "30th", "31st"} 中的一个元素。
Month 是集合 {"Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"} 中的一个元素。
Year 的范围在 [1900, 2100] 之间。
请你将字符串转变为 YYYY-MM-DD 的格式，其中：

YYYY 表示 4 位的年份。
MM 表示 2 位的月份。
DD 表示 2 位的天数。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/reformat-date
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var reformatDate = function(date) {
  const Month = {"Jan": "01", "Feb": "02", "Mar": "03", "Apr": "04", "May": "05", "Jun": "06", "Jul": "07", "Aug": "08", "Sep": "09", "Oct": "10", "Nov": "11", "Dec": "12"};
  const dateArr = date.split(" ");
  const year = dateArr[2];
  const mon = Month[dateArr[1]];
  let day = dateArr[0].replace(/st|nd|rd|th/g, '');
  if( Number(day) < 10) {
    day = `0${day}`;
  }

  return `${year}-${mon}-${day}`;
};
```


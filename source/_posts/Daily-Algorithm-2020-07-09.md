---
title: Daily-Algorithm-2020-07-09
date: 2020-07-09 09:14:06
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [一周中的第几天](https://leetcode-cn.com/problems/day-of-the-week/)

## Desc

给你一个日期，请你设计一个算法来判断它是对应一周中的哪一天。

输入为三个整数：day、month 和 year，分别表示日、月、年。

您返回的结果必须是这几个值中的一个 {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"}。

 

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/day-of-the-week
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var dayOfTheWeek = function(day, month, year) {
  const objs = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
  const date = new Date(`${year}-${month}-${day}`).getDay();

  return objs[date];
};
```


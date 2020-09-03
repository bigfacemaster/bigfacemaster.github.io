---
title: Daily-Algorithm-2020-09-03
date: 2020-09-03 09:15:00
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [ 字符串中的单词数](https://leetcode-cn.com/problems/number-of-segments-in-a-string/)

## Desc

统计字符串中的单词个数，这里的单词指的是连续的不是空格的字符。

请注意，你可以假定字符串里不包括任何不可打印的字符。



## Code

```js
var countSegments = function(s) {
  return s.split(' ').filter((item) => item !== "").length;
};
```


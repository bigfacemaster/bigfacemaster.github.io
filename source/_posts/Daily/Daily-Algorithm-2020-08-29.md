---
title: Daily-Algorithm-2020-08-29
date: 2020-08-29 23:14:53
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [键盘行](https://leetcode-cn.com/problems/keyboard-row/)

## Desc

给定一个单词列表，只返回可以使用在键盘同一行的字母打印出来的单词。键盘如下图所示。

**注意：**

1. 你可以重复使用键盘上同一字符。
2. 你可以假设输入的字符串将只包含字母。



## Code

```js
var findWords = function(words) {
  return words.filter(x => /(^[qwertyuiop]+$)|(^[asdfghjkl]+$)|(^[zxcvbnm]+$)/i.test(x));
}
```


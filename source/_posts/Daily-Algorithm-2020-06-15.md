---
title: Daily-Algorithm-2020-06-15
date: 2020-06-15 09:35:59
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---



# [检测大写字母](https://leetcode-cn.com/problems/detect-capital/)

## Desc

给定一个单词，你需要判断单词的大写使用是否正确。

我们定义，在以下情况时，单词的大写用法是正确的：

全部字母都是大写，比如"USA"。
单词中所有字母都不是大写，比如"leetcode"。
如果单词不只含有一个字母，只有首字母大写， 比如 "Google"。
否则，我们定义这个单词没有正确使用大写字母。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/detect-capital
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var detectCapitalUse = function(word) {
  return /^[A-Z]+$/.test(word) || /^[A-Z][a-z]{1,}$/.test(word) || /^[a-z]+$/.test(word)
};
```


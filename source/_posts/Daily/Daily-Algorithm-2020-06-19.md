---
title: Daily-Algorithm-2020-06-19
date: 2020-06-19 09:39:27
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [验证回文串](https://leetcode-cn.com/problems/valid-palindrome/)

## Desc

给定一个字符串，验证它是否是回文串，只考虑字母和数字字符，可以忽略字母的大小写。

**说明：**本题中，我们将空字符串定义为有效的回文串。



## Code

```js
const isPalindrome = (s) => {
  let pureString = s.replace(/[^A-Za-z0-9]/g, '').toLocaleLowerCase();
  let reverseStr = pureString.split('').reverse().join('');
  return pureString == reverseStr;
};
```


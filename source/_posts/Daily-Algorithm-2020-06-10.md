---
title: Daily-Algorithm-2020-06-10
date: 2020-06-11 11:04:39
tags: Algorithm, 算法
category: Algorithm, 算法
---



# [回文数](https://leetcode-cn.com/problems/palindrome-number/)

## Desc

判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。



## 题解(JS)

```js
const isPalindrom = str => str.toString() === str.toString().split("").reverse().join("");

isPalindrome('-121'); // false
isPalindrome(121);    // true
```


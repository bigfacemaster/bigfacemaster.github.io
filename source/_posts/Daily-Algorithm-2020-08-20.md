---
title: Daily-Algorithm-2020-08-20
date: 2020-08-20 10:24:03
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [有效的字母异位词](https://leetcode-cn.com/problems/valid-anagram/)

## Desc

给定两个字符串 *s* 和 *t* ，编写一个函数来判断 *t* 是否是 *s* 的字母异位词。



## Code

```js
var isAnagram = function(s, t) {
  if(s.length !== t.length) {
    return false;
  }
  let result = true;
  const sA = s.split('').sort();
  const tA = t.split('').sort();
  for(let i = 0; i < sA.length; i++) {
    if(sA[i] !== tA[i]) {
      return false;
    }
  }

  return result;
};
```


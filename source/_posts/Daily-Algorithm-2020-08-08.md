---
title: Daily-Algorithm-2020-08-08
date: 2020-08-08 13:33:55
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [ 3的幂](https://leetcode-cn.com/problems/power-of-three/)

## Desc



给定一个整数，写一个函数来判断它是否是 3 的幂次方。



## Code

```js
var isPowerOfThree = function(n) {
  if(n <= 0) {
    return false;
  }
  while(n > 1) {
      if( n%3 === 0) {
          n = n/ 3
      } else {
          return false
      }
  }
  return true;
};
```


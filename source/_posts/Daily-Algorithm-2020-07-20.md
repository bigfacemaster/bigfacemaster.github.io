---
title: Daily-Algorithm-2020-07-20
date: 2020-07-20 09:37:24
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [三角形的最大周长](https://leetcode-cn.com/problems/largest-perimeter-triangle/)

## Desc

给定由一些正数（代表长度）组成的数组 `A`，返回由其中三个长度组成的、**面积不为零**的三角形的最大周长。

如果不能形成任何面积不为零的三角形，返回 `0`。



## Code

```js
var largestPerimeter = function(A) {
  const sortedA = A.sort((a, b) => a - b);
  for (let i = sortedA.length - 3; i >= 0; --i) {
    if (sortedA[i] + sortedA[i+1] > sortedA[i+2]) {
      return sortedA[i] + sortedA[i+1] + sortedA[i+2];
    }
  }
  return 0;
};
```


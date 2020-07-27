---
title: Daily-Algorithm-2020-07-27
date: 2020-07-27 09:30:08
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [最小绝对差](https://leetcode-cn.com/problems/minimum-absolute-difference/)

## Desc

给你个整数数组 `arr`，其中每个元素都 **不相同**。

请你找到所有具有最小绝对差的元素对，并且按升序的顺序返回。



## Code

```js
var minimumAbsDifference = function(arr) {
  const sortedArr = arr.sort((a, b) => a - b);
  let min = Infinity;
  for(let i = 1; i < sortedArr.length; i++) {
    const differ = sortedArr[i] - sortedArr[i-1];
    if(differ < min) {
      min = differ;
    }
  }

  const result = [];
  for(let i = 1; i < sortedArr.length; i++) {
    const differ = sortedArr[i] - sortedArr[i-1];
    if(differ === min) {
      result.push([sortedArr[i-1], sortedArr[i]])
    }
  }
  return result;
};
```


---
title: Daily-Algorithm-2020-08-03
date: 2020-08-03 08:58:18
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [有效的山脉数组](https://leetcode-cn.com/problems/valid-mountain-array/)

## Desc

给定一个整数数组 A，如果它是有效的山脉数组就返回 true，否则返回 false。

让我们回顾一下，如果 A 满足下述条件，那么它是一个山脉数组：

A.length >= 3
在 0 < i < A.length - 1 条件下，存在 i 使得：
A[0] < A[1] < ... A[i-1] < A[i]
A[i] > A[i+1] > ... > A[A.length - 1]

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/valid-mountain-array
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var validMountainArray = function(A) {
  // 找到最大值的索引，然后判断其左端的值是否为升序，右端的为降序；
  if(A.length < 3) {
    return false;
  }
  const max = Math.max(...A);
  const maxIndex = A.findIndex(v => v === max);
  if(maxIndex) {
    const left = A.slice(0, maxIndex + 1);
    const right = A.slice(maxIndex, A.length);
    return isAscende(left) && isDescende(right);
  }
  return false;
};

const isAscende = A => {
  if(A.length < 2) {
    return false;
  }
  let result = true;
  for(let i = 1; i < A.length; i++) {
    if(A[i - 1] >= A[i]) {
      result = false;
      return false;
    }
  }
  return result;
}

const isDescende = A => {
  if(A.length < 2) {
    return false;
  }
  let result = true;
  for(let i = 1; i < A.length; i++) {
    if(A[i] >= A[i-1]) {
      result = false;
      return false;
    }
  }
  return result;
}
```


---
title: Daily-Algorithm-2020-08-24
date: 2020-08-24 09:07:09
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [单调数列](https://leetcode-cn.com/problems/monotonic-array/)

## Desc

如果数组是单调递增或单调递减的，那么它是单调的。

如果对于所有 i <= j，A[i] <= A[j]，那么数组 A 是单调递增的。 如果对于所有 i <= j，A[i]> = A[j]，那么数组 A 是单调递减的。

当给定的数组 A 是单调数组时返回 true，否则返回 false。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/monotonic-array
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var isMonotonic = function(A) {
  const temp = [...new Set(A)]
  if(temp.length > 2) {
    let ascending = temp[0] <= temp[1];
    if(temp[0] === temp[1]) {
      ascending = temp[1] <= temp[2];
    }
    for(let i = 1; i < A.length; i++) {
      if(ascending) {
        if(A[i - 1] > A[i]) {
          return false;
        }
      } else if(A[i - 1] < A[i]){
        return false;
      }
    }
    return true;
  }
  return true;
};
```


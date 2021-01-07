---
title: Daily-Algorithm-2020-09-08
date: 2020-09-08 09:18:41
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [按奇偶排序数组 II](https://leetcode-cn.com/problems/sort-array-by-parity-ii/)

## Desc

给定一个非负整数数组 A， A 中一半整数是奇数，一半整数是偶数。

对数组进行排序，以便当 A[i] 为奇数时，i 也是奇数；当 A[i] 为偶数时， i 也是偶数。

你可以返回任何满足上述条件的数组作为答案。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/sort-array-by-parity-ii
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var sortArrayByParityII = function(A) {
  const events = A.filter(v => v % 2 === 0);
  const odds = A.filter(v => v % 2 === 1);
  const result = [];
  events.forEach((v, i) => {
    result.push(events[i]);
    result.push(odds[i]);
  });
  return result;
};
```


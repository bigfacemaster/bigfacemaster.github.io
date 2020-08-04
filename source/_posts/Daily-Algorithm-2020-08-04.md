---
title: Daily-Algorithm-2020-08-04
date: 2020-08-04 10:34:23
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [数组形式的整数加法](https://leetcode-cn.com/problems/add-to-array-form-of-integer/)

## Desc

对于非负整数 X 而言，X 的数组形式是每位数字按从左到右的顺序形成的数组。例如，如果 X = 1231，那么其数组形式为 [1,2,3,1]。

给定非负整数 X 的数组形式 A，返回整数 X+K 的数组形式。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/add-to-array-form-of-integer
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var addToArrayForm = function(A, K) {
  const num = Number(A.join(''));
  return String(num + K).split('');
};
```


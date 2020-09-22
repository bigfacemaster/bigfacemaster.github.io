---
title: Daily-Algorithm-2020-09-19
date: 2020-09-20 19:44:26
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [旋转字符串](https://leetcode-cn.com/problems/rotate-string/)

## Desc

给定两个字符串, A 和 B。

A 的旋转操作就是将 A 最左边的字符移动到最右边。 例如, 若 A = 'abcde'，在移动一次之后结果就是'bcdea' 。如果在若干次旋转操作之后，A 能变成B，那么返回True。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/rotate-string
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code	

```js
var rotateString = function(A, B) {
  return A.length <= B.length && (A + A).includes(B);
};
```


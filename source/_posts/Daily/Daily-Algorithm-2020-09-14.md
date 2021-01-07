---
title: Daily-Algorithm-2020-09-14
date: 2020-09-14 09:25:29
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [可被 5 整除的二进制前缀](https://leetcode-cn.com/problems/binary-prefix-divisible-by-5/)

## Desc

给定由若干 0 和 1 组成的数组 A。我们定义 N_i：从 A[0] 到 A[i] 的第 i 个子数组被解释为一个二进制数（从最高有效位到最低有效位）。

返回布尔值列表 answer，只有当 N_i 可以被 5 整除时，答案 answer[i] 为 true，否则为 false。



来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/binary-prefix-divisible-by-5
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var prefixesDivBy5 = function(A) {
  const result = []; 
  let middle = 0;

  for( var i = 0; i < A.length; i++){
    middle = middle * 2 + A[i]
    result.push((middle % 5 == 0)? true : false)
    middle = middle % 10
  }
  return result;
};
```


---
title: Daily-Algorithm-2020-08-17
date: 2020-08-17 09:28:44
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [公平的糖果交换](https://leetcode-cn.com/problems/fair-candy-swap/)

## Desc

爱丽丝和鲍勃有不同大小的糖果棒：A[i] 是爱丽丝拥有的第 i 块糖的大小，B[j] 是鲍勃拥有的第 j 块糖的大小。

因为他们是朋友，所以他们想交换一个糖果棒，这样交换后，他们都有相同的糖果总量。（一个人拥有的糖果总量是他们拥有的糖果棒大小的总和。）

返回一个整数数组 ans，其中 ans[0] 是爱丽丝必须交换的糖果棒的大小，ans[1] 是 Bob 必须交换的糖果棒的大小。

如果有多个答案，你可以返回其中任何一个。保证答案存在。

 

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/fair-candy-swap
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var fairCandySwap = function(A, B) {
  let sum1 = A.reduce((prev,next) => prev + next)
  let sum2 = B.reduce((prev,next) => prev + next)
  let gap = (sum1 - sum2) / 2
  for (let i = 0; i < A.length; i++) {
    if(B.includes(A[i]-gap)){
      return [A[i],A[i]-gap]
    }
  }
};
```


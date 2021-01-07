---
title: Daily-Algorithm-2020-06-17
date: 2020-06-17 09:40:14
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [最佳观光组合](https://leetcode-cn.com/problems/best-sightseeing-pair/)

## Desc

给定正整数数组 A，A[i] 表示第 i 个观光景点的评分，并且两个景点 i 和 j 之间的距离为 j - i。

一对景点（i < j）组成的观光组合的得分为（A[i] + A[j] + i - j）：景点的评分之和减去它们两者之间的距离。

返回一对观光景点能取得的最高分。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/best-sightseeing-pair
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
const maxScoreSightseeingPair = function(A) {
  // left = A[i] + i; right = A[j] - j; 
  let left = A[0] + 0; 
  let result = -Infinity;
  for(let next = 1; next < A.length; next ++) {
    result = Math.max(result, left + A[next] - next);
    left = Math.max(left, A[next] + next);
  }
  return result;
};
```


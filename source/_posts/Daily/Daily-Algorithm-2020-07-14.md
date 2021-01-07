---
title: Daily-Algorithm-2020-07-14
date: 2020-07-14 09:59:27
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [一维数组的动态和](https://leetcode-cn.com/problems/running-sum-of-1d-array/)

## Desc

给你一个数组 nums 。数组「动态和」的计算公式为：runningSum[i] = sum(nums[0]…nums[i]) 。

请返回 nums 的动态和。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/running-sum-of-1d-array
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var runningSum = function(nums) {
  const result = [];
  nums.forEach(( v, k) => {
    result.push(sum(nums.slice(0, k + 1)));
  })
  return result;
};

const sum = arr => {
  let result = 0;
  for(let v of arr) {
    result += v;
  }
  return result;
}
```


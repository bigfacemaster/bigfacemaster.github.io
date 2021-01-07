---
title: Daily-Algorithm-2020-07-01
date: 2020-07-01 09:04:09
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [重新排列数组](https://leetcode-cn.com/problems/shuffle-the-array/)

## Desc

给你一个数组 nums ，数组中有 2n 个元素，按 [x1,x2,...,xn,y1,y2,...,yn] 的格式排列。

请你将数组按 [x1,y1,x2,y2,...,xn,yn] 格式重新排列，返回重排后的数组。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/shuffle-the-array
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var shuffle = function(nums, n) {
  const xArr = nums.slice(0, n);
  const yArr = nums.slice(n, nums.length);
  const result = [];
  xArr.forEach((v, k) => {
    result.push(v);
    result.push(yArr[k]);
  })
  return result;
};
```


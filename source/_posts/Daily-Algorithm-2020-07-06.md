---
title: Daily-Algorithm-2020-07-06
date: 2020-07-06 09:56:11
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [数组中两元素的最大乘积](https://leetcode-cn.com/problems/maximum-product-of-two-elements-in-an-array/)

## Desc

给你一个整数数组 nums，请你选择数组的两个不同下标 i 和 j，使 (nums[i]-1)*(nums[j]-1) 取得最大值。

请你计算并返回该式的最大值。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/maximum-product-of-two-elements-in-an-array
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var maxProduct = function(nums) {
  const result = [];
  for(let i = 0; i < nums.length; i++) {
    const num1 = nums[i];
    for(let j = 0; j < nums.length; j++) {
      if( i !== j) {
        result.push((num1 - 1) * (nums[j] - 1));
      }
    }
  }
  return Math.max(...result);
};
```


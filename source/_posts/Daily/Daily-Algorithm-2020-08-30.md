---
title: Daily-Algorithm-2020-08-30
date: 2020-08-30 14:37:26
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [下一个更大元素 I](https://leetcode-cn.com/problems/next-greater-element-i/)

## Desc

给定两个 没有重复元素 的数组 nums1 和 nums2 ，其中nums1 是 nums2 的子集。找到 nums1 中每个元素在 nums2 中的下一个比其大的值。

nums1 中数字 x 的下一个更大元素是指 x 在 nums2 中对应位置的右边的第一个比 x 大的元素。如果不存在，对应位置输出 -1 。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/next-greater-element-i
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var nextGreaterElement = function(nums1, nums2) {
   return nums1.map(num1 => nums2.slice(nums2.indexOf(num1) + 1).find(num2 => num2 > num1) || -1);
};
```


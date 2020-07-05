---
title: Daily-Algorithm-2020-07-05
date: 2020-07-05 15:48:49
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [ 数组序号转换](https://leetcode-cn.com/problems/rank-transform-of-an-array/)

## Desc

给你一个整数数组 arr ，请你将数组中的每个元素替换为它们排序后的序号。

序号代表了一个元素有多大。序号编号的规则如下：

* 序号从 1 开始编号
*  一个元素越大，那么序号越大。如果两个元素相等，那么它们的序号相同。
* 每个数字的序号都应该尽可能地小。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/rank-transform-of-an-array
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

## Code



```js
var arrayRankTransform = function(arr) {
    const newArr = [...new Set(arr)].sort((a, b) => a - b );
    const result = [];
    arr.forEach(v => {
      result.push(newArr.findIndex(i => i === v) + 1);
    });
    return result;
};
```


---
title: Daily-Algorithm-2020-07-28
date: 2020-07-28 09:24:43
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [数组的相对排序](https://leetcode-cn.com/problems/relative-sort-array/)

## Desc

给你两个数组，arr1 和 arr2，

arr2 中的元素各不相同
arr2 中的每个元素都出现在 arr1 中
对 arr1 中的元素进行排序，使 arr1 中项的相对顺序和 arr2 中的相对顺序相同。未在 arr2 中出现过的元素需要按照升序放在 arr1 的末尾。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/relative-sort-array
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var relativeSortArray = function(arr1, arr2) {
  const result = [];
  arr2.forEach(v => {
    const temp = arr1.filter(i => i === v);
    result.push(...temp);
  });
  const other = [];
  arr1.forEach(v => {
    const temp = arr2.find(i => i === v);
    if(temp === undefined) {
      other.push(v)
    }
  });
  return [...result, ...other.sort((a, b) => a - b)];
};
```


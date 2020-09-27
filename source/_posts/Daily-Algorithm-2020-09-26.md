---
title: Daily-Algorithm-2020-09-26
date: 2020-09-26 21:43:38
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [找出数组中的幸运数](https://leetcode-cn.com/problems/find-lucky-integer-in-an-array/)

## Desc

在整数数组中，如果一个整数的出现频次和它的数值大小相等，我们就称这个整数为「幸运数」。

给你一个整数数组 arr，请你从中找出并返回一个幸运数。

如果数组中存在多个幸运数，只需返回 最大 的那个。
如果数组中不含幸运数，则返回 -1 。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/find-lucky-integer-in-an-array
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var findLucky = function(arr) {
    let obj = {};
    arr.forEach((x) => {
        obj[x] = (x in obj ? obj[x] + 1 : 1);
    });
    let result = -1;
    Object.keys(obj).forEach((key) => {
        result = (key == obj[key] ? Math.max(key, result) : result);
    });
    return result;
};
```


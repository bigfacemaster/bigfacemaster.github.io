---
title: Daily-Algorithm-2020-09-12
date: 2020-09-12 16:26:10
tags:tags: [Algorithm, 算法]
category: [Algorithm, 算法]:
---

# [检查整数及其两倍数是否存在](https://leetcode-cn.com/problems/check-if-n-and-its-double-exist/)

## Desc


给你一个整数数组 `arr`，请你检查是否存在两个整数 `N` 和 `M`，满足 `N` 是 `M` 的两倍（即，`N = 2 * M`）。

更正式地，检查是否存在两个下标 `i` 和 `j` 满足：

- `i != j`
- `0 <= i, j < arr.length`
- `arr[i] == 2 * arr[j]`

## Code

```js
var checkIfExist = function(arr) {
  const set = new Set();
  for (const val of arr) {
    if (set.has(val << 1) || set.has(val / 2)) return true;
    set.add(val);
  }
  return false;
};
```


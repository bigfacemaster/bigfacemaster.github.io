---
title: Daily-Algorithm-2020-09-25
date: 2020-09-25 09:52:42
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [拿硬币](https://leetcode-cn.com/problems/na-ying-bi/)

## Desc

桌上有 `n` 堆力扣币，每堆的数量保存在数组 `coins` 中。我们每次可以选择任意一堆，拿走其中的一枚或者两枚，求拿完所有力扣币的最少次数。



## Code	

```js
var minCount = function(coins) {
  let result = 0;
  for(let i = 0; i < coins.length; i++){
      result += coins[i] % 2 == 0 ? coins[i] / 2 : parseInt(coins[i] / 2) + 1
  }
  return result;
};
```


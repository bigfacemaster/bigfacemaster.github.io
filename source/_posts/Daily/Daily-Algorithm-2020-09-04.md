---
title: Daily-Algorithm-2020-09-04
date: 2020-09-04 09:49:35
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [排列硬币](https://leetcode-cn.com/problems/arranging-coins/)

## Desc

你总共有 n 枚硬币，你需要将它们摆成一个阶梯形状，第 k 行就必须正好有 k 枚硬币。

给定一个数字 n，找出可形成完整阶梯行的总行数。

n 是一个非负整数，并且在32位有符号整型的范围内。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/arranging-coins
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var arrangeCoins = function(n) {
  let num = n;
  let line = 1
  if (num == 0) {
    return 0;
  }
  while (num > 0) {
    num = num - line
    line++;
    if (num < line){ 
      return line - 1;
    }
  }
};
```


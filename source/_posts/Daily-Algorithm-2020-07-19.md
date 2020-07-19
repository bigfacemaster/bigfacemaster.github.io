---
title: Daily-Algorithm-2020-07-19
date: 2020-07-19 08:52:16
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [最后一块石头的重量](https://leetcode-cn.com/problems/last-stone-weight/)

## Desc

有一堆石头，每块石头的重量都是正整数。

每一回合，从中选出两块 最重的 石头，然后将它们一起粉碎。假设石头的重量分别为 x 和 y，且 x <= y。那么粉碎的可能结果如下：

如果 x == y，那么两块石头都会被完全粉碎；
如果 x != y，那么重量为 x 的石头将会完全粉碎，而重量为 y 的石头新重量为 y-x。
最后，最多只会剩下一块石头。返回此石头的重量。如果没有石头剩下，就返回 0。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/last-stone-weight
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var lastStoneWeight = function(stones) {
  const sorted = stones.sort((a, b) => b - a);
  if(sorted.length > 1) {
    const difference = sorted[0] - sorted[1];
    const temp = sorted.slice(2) || [0];
    if(difference) {
      temp.push(difference);
    }
    return lastStoneWeight(temp);
  }
  return sorted[0] || 0;
};
```


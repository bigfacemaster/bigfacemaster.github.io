---
title: Daily-Algorithm-2020-07-07
date: 2020-07-07 08:53:40
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [多数元素](https://leetcode-cn.com/problems/majority-element/)

## Desc

给定一个大小为 n 的数组，找到其中的多数元素。多数元素是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。

你可以假设数组是非空的，并且给定的数组总是存在多数元素。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/majority-element
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var majorityElement = function(nums) {
  const standard = Math.ceil(nums.length / 2);
  let result = undefined;
  const noRepeat = [...new Set(nums)];
  for(let i = 0; i < noRepeat.length; i++) {
    const same = nums.filter(v => v === noRepeat[i]);
    if(same.length >= standard) {
      result = noRepeat[i];
    }
  }
  return result;
};
```


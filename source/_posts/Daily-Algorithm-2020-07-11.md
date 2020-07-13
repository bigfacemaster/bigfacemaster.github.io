---
title: Daily-Algorithm-2020-07-11
date: 2020-07-11 21:30:18
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [ 自除数](https://leetcode-cn.com/problems/self-dividing-numbers/)

## Desc

自除数 是指可以被它包含的每一位数除尽的数。

例如，128 是一个自除数，因为 128 % 1 == 0，128 % 2 == 0，128 % 8 == 0。

还有，自除数不允许包含 0 。

给定上边界和下边界数字，输出一个列表，列表的元素是边界（含边界）内所有的自除数。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/self-dividing-numbers
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var selfDividingNumbers = function(left, right) {
  const result = []
  for(let i = left; i < right + 1; i++) {
    if(isDivide(i)) {
      result.push(i)
    }
  }
  return result;
};

const isDivide = v => {
  if(v < 10) {
    return true;
  }
  let result = true;
  const arr = `${v}`.split('');
  for(let i = 0; i < arr.length; i++) {
    if(v % arr[i] !== 0 ) {
      result = false;
    }
  }
  return result;
}
```


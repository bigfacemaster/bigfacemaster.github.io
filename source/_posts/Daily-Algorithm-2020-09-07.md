---
title: Daily-Algorithm-2020-09-07
date: 2020-09-07 09:21:43
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [ 比较含退格的字符串](https://leetcode-cn.com/problems/backspace-string-compare/)

## Desc

给定 S 和 T 两个字符串，当它们分别被输入到空白的文本编辑器后，判断二者是否相等，并返回结果。 # 代表退格字符。

注意：如果对空文本输入退格字符，文本继续为空。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/backspace-string-compare
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var backspaceCompare = function(S, T) {
    const arrS = S.split('');
    const arrT = T.split('');
    const result1 = [];
    const result2 = [];
    arrS.forEach(v => {
      if(v === '#' ) {
        result1.pop();
      } else {
        result1.push(v);
      }
    });
    arrT.forEach(v => {
      if(v === '#' ) {
        result2.pop();
      } else {
        result2.push(v);
      }
    });

    return result1.join() === result2.join();
};
```


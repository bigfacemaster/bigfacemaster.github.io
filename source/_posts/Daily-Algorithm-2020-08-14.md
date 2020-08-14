---
title: Daily-Algorithm-2020-08-14
date: 2020-08-14 09:21:34
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [1比特与2比特字符](https://leetcode-cn.com/problems/1-bit-and-2-bit-characters/)

## Desc

有两种特殊字符。第一种字符可以用一比特0来表示。第二种字符可以用两比特(10 或 11)来表示。

现给一个由若干比特组成的字符串。问最后一个字符是否必定为一个一比特字符。给定的字符串总是由0结束。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/1-bit-and-2-bit-characters
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var isOneBitCharacter = function(bits) {
  return /^(10|11|0)*0$/.test(bits.join(''));
};
```


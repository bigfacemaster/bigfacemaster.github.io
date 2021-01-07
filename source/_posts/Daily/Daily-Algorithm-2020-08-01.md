---
title: Daily-Algorithm-2020-08-01
date: 2020-08-01 19:51:39
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [寻找比目标字母大的最小字母](https://leetcode-cn.com/problems/find-smallest-letter-greater-than-target/)

## Desc

给你一个排序后的字符列表 letters ，列表中只包含小写英文字母。另给出一个目标字母 target，请你寻找在这一有序列表里比目标字母大的最小字母。

在比较时，字母是依序循环出现的。举个例子：

如果目标字母 target = 'z' 并且字符列表为 letters = ['a', 'b']，则答案返回 'a'

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/find-smallest-letter-greater-than-target
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var nextGreatestLetter = function(letters, target) {
  const result = comapre(letters, target);
  return result || letters[0];
};

const comapre  = (letters, target) => {
  const alphabet = {
    a:1, b: 2, c: 3, d:4, e:5, f:6, g:7, h:8, i:9, j: 10, k: 11, l: 12, m: 13, n: 14, o: 15, p: 16, q: 17, r: 18, s: 19, t: 20, u: 21, v: 22,  w: 23, x: 24, y : 25,  z: 26
  };

  for(let i = 0; i < letters.length; i++) {
    if(alphabet[letters[i]] > alphabet[target]) {
      return letters[i];
    }
  }
}
```


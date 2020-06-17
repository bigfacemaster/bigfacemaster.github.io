---
title: Daily-Algorithm-2020-06-12
date: 2020-06-12 10:58:03
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---



# [[最长公共前缀](https://leetcode-cn.com/problems/longest-common-prefix/)](https://leetcode-cn.com/problems/roman-to-integer/)

## Desc

编写一个函数来查找字符串数组中的最长公共前缀。

如果不存在公共前缀，返回空字符串 `""`。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/detect-capital
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## 题解(JS)



```js
const longestCommonPrefix = function(strs) {
  
  let result = strs[0] ? strs[0]:'';

  for(let i = 1; i < strs.length; i ++) {

    let regex = new RegExp('^' + result);

    while (!regex.test(strs[i]) && result.length) {
      result = result.slice(0, result.length - 1);
      regex = new RegExp('^' + result)
    }
  }
  return result;
};
```


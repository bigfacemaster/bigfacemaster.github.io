---
title: Daily-Algorithm-2020-09-13
date: 2020-09-13 16:41:24
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [密钥格式化](https://leetcode-cn.com/problems/license-key-formatting/)

## Desc

有一个密钥字符串 S ，只包含字母，数字以及 '-'（破折号）。其中， N 个 '-' 将字符串分成了 N+1 组。

给你一个数字 K，请你重新格式化字符串，除了第一个分组以外，每个分组要包含 K 个字符；而第一个分组中，至少要包含 1 个字符。两个分组之间需要用 '-'（破折号）隔开，并且将所有的小写字母转换为大写字母。

给定非空字符串 S 和数字 K，按照上面描述的规则进行格式化。



来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/license-key-formatting
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code	

```js
var licenseKeyFormatting = function(S, K) {
    let arr = S.replace(/-/g,'').toUpperCase().split('');
    let temp = 0;
    for(let i = arr.length - 1; i > 0; i--){
        ++temp;
        if(temp===K){
            arr.splice(i,0,'-');
            temp = 0;
        }
    }
    return arr.join('');
}
```


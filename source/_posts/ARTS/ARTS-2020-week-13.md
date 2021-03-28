---
title: ARTS-2020-week-13
tags:
  - ARTS
  - Algorithm
  - Review
  - Tip
  - Share
  - 算法
  - 阅读
  - 技巧
  - 分享
date: 2021-03-26 21:07:29
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

#### [交替合并字符串](https://leetcode-cn.com/problems/merge-strings-alternately/)

给你两个字符串 word1 和 word2 。请你从 word1 开始，通过交替添加字母来合并字符串。如果一个字符串比另一个字符串长，就将多出来的字母追加到合并后字符串的末尾。

返回 合并后的字符串 。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/merge-strings-alternately
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



```js
var mergeAlternately = function(word1, word2) {
    let words1Arr= word1.split('');
    let words2Arr = word2.split('');
    let res = [];
    while(words1Arr.length && words2Arr.length){
        res.push(words1Arr.shift());
        res.push(words2Arr.shift());
    }
    return [...res,...words1Arr,...words2Arr].join('');
};
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

# [A Complete Guide To Accessible Front-End Components](https://www.smashingmagazine.com/2021/03/complete-guide-accessible-front-end-components/)



# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

利用 **verdaccio** 部署私有 **npm** 仓库，并发布，然后针对私有 **npm**，进行登录发布

```sh
npm publish:
npm login --registry npm-host
npm username/paddword

lerna publish

npm logout npm-host
```



# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

> Null
---
title: ARTS-2020-week-02.md
date: 2021-01-03 17:56:22
tags: [ARTS]
category: [ARTS]
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

# [杨辉三角](https://leetcode-cn.com/problems/pascals-triangle/)

给定一个非负整数 *numRows，*生成杨辉三角的前 *numRows* 行。

```js
const triangle = (pre, line) => {
  const result = [];
  const param = pre[pre.length - 1];
  
  for (i = 0; i < param.length + 1; i++) {
    const first = Number(param[i - 1] || 0);
    const send = Number(param[i] || 0);
    result.push(first + send); 
  }
  
  return result;
}

const generater = (numRows) => {
  const result = [];
  for (i = 1; i < numRows + 1; i++) {
    if (i === 1) {
      result.push([1]);
    } else if (i === 2) {
      result.push([1, 1]);
    } else if (i > 2){
      result.push(triangle(result, i));
    }
  }
  return result;
}
```





# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文



# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点



# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

git merge vs rebase





![get](http://bigfacemaster.test.upcdn.net/uPic/sZVajS.png)


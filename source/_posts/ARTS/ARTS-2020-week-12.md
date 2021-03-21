---
title: ARTS-2020-week-12
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
date: 2021-03-15 11:13:26
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

> 冒泡排序(Bubble Sort)

```js
const bubbleSort = (arr) => {
  const length = arr?.length ?? 0;
  if( length <= 1 ) {
    return arr;
  } else {
    for( let i = 0; i < length; ++i ) {
      let falg = false;
      for( let j = 0; j < length - i - 1; ++j ) {
        if ( arr[j] > arr[j+1]) {
          let tmp = arr[j];
          arr[j] = arr[j + 1];
          arr[j + 1] = temp;
          flag = true;
        }
      }
      if(!flag) {
        break;
      }
    }
    return arr;
   }
}
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

## How DevOps Brings Out The Best In Developers

1.  DevOps helps developers and programmers to think automation
2.  A source of new skills
3.  You build it - you run it
4.  Collaboration and transparency


# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

使用 lerna + verdaccio 进行公司内部的组件库的搭建。build采用 [father](https://github.com/umijs/father)，使用ts

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

> Null
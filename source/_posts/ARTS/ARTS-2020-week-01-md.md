---
title: ARTS-2020-week-01.md
date: 2021-01-01 17:56:18
tags: [ARTS]
category: [ARTS]
---



# Algorithm

> 每周一个算法题：为了编程训练和学习

## [斐波那契数](https://leetcode-cn.com/problems/fibonacci-number/)

Desc: 斐波那契数，通常用 F(n) 表示，形成的序列称为 斐波那契数列 。该数列由 0 和 1 开始，后面的每一项数字都是前面两项数字的和。也就是：

F(0) = 0，F(1) = 1
F(n) = F(n - 1) + F(n - 2)，其中 n > 1
给你 n ，请计算 F(n) 。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/fibonacci-number
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



```js
var fib = function(n) {
  if (n === 0 || n === 1 ) {
    return n;
  } else {
    return fib(n - 1) + fib(n - 2);
  }
};
```



# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

[Why you should choose useState instead of useReducer](https://medium.com/free-code-camp/why-you-should-choose-usestate-instead-of-usereducer-ffc80057f815)

作者从**useState**扩展到**useReducer**，最后到**redux**，简单实用**useState**，复杂使用**useReducer**，实现了一个简单的**redux**。

具体的应用场景还需要具体的分析，页面简单级使用**useState**的效率更高，随着复杂度的提高使用**useReducer**更能统一管理，与全局的调用（**redux**），最后感叹一句：**万物皆可 [hooks](https://reactjs.org/docs/hooks-intro.html) **





# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

**React useReducer**

基本上没有注意过这个**hooks**，今天在做review的时候，仔细看了一下。

```tsx
const [state, dispatch] = useReducer(reducer, initialArg, init);
```



从我的理解来说，如同一个简易版的**redux**来完成一些复杂的**useState**功能，便于全局性的使用。

我个人来说还是更加倾向于使用**useState**



# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

[ant-design-upgrade && jsx to tsx]()

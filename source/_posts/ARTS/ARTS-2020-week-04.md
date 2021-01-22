---
title: ARTS-2020-week-04
tags:
  - ARTS
  - Algorithm
  - Review
  - Tip
  - Share
  - 算法
  - 阅读， 技巧， 分享
date: 2021-01-17 20:13:37
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

## [数组形式的整数加法](https://leetcode-cn.com/problems/add-to-array-form-of-integer/)

对于非负整数 X 而言，X 的数组形式是每位数字按从左到右的顺序形成的数组。例如，如果 X = 1231，那么其数组形式为 [1,2,3,1]。

给定非负整数 X 的数组形式 A，返回整数 X+K 的数组形式。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/add-to-array-form-of-integer
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

```````tsx
const addToArrayForm = (A: number[], K:number) => {
  const num = Number(A.join(''));
  return String(num + K).split('');
};
```````




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文



# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

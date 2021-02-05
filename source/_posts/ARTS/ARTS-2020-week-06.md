---
title: ARTS-2020-week-06
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
date: 2021-02-01 09:35:56
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

#### [剑指 Offer 03. 数组中重复的数字](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)

找出数组中重复的数字。


在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



```tsx
const findRepeatNumber = (nums) => {
  const uniqArr = [...new Set(nums)];
  let result = [];
  uniqArr.forEach(v => {
    const temp = nums.filter(i => i === v);
    if(temp.length > result.length) {
      result = temp;
    }
  })
  return result[0];
};
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

[styling-web-components](https://css-tricks.com/styling-web-components/)



# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

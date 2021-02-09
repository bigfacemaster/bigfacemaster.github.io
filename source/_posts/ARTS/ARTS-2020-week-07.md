---
title: ARTS-2020-week-07
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
date: 2021-02-09 09:15:46
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

## [剑指 Offer 03. 数组中重复的数字](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)

找出数组中重复的数字。


在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。



来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



> 思路：先遍历数组，得到一个object，然后再遍历数组，将出现的数字进行计数，最后遍历对象，得到最大的出现次数（max - 1）以及出现的最大值。

```javascript
const findRepeatNumber = (nums) => {
  const obj = {};
  nums.forEach(v => obj[v] = 1);

  nums.forEach(v => {
    obj[v] = obj[v] + 1;
  })
  let result = nums[0];
  let max = 0;
  for (const [key, value] of Object.entries(obj)) {
    if(Math.max(max, value) === value) {
      max = value;
      result = key;
    }
  }
  
  return result;
};
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

## [Exploring the Complexities of Width and Height in CSS](https://css-tricks.com/exploring-the-complexities-of-width-and-height-in-css/)

探索了 盒子模型以及能够真实影响到元素宽度的属性。

```css
/* Width */
width + padding-left + padding-right + border-left + border-right

/* Height */
height + padding-top + padding-bottom + border-top + border-bottom
```

以及**display**属性的值对其的影响。以及动态宽度的计算，来达到想要的真实宽度以及高度等信息。


# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

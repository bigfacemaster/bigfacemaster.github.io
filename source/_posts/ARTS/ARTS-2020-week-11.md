---
title: ARTS-2020-week-11
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
date: 2021-03-08 09:16:25
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

#### [剑指 Offer 53 - II. 0～n-1中缺失的数字](https://leetcode-cn.com/problems/que-shi-de-shu-zi-lcof/)

一个长度为n-1的递增排序数组中的所有数字都是唯一的，并且每个数字都在范围0～n-1之内。在范围0～n-1内的n个数字中有且只有一个数字不在该数组中，请找出这个数字。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/que-shi-de-shu-zi-lcof
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



```js
var missingNumber = function(nums) {
  const sum1 = nums.reduce((a, b) => a + b);
  const sum2 = (nums.length + 1) * nums.length / 2;
  return sum2 - sum1;
};
```



# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

[ECMAScript 2021: the final feature set](https://2ality.com/2020/09/ecmascript-2021.html)

* [`String.prototype.replaceAll`](https://exploringjs.com/impatient-js/ch_regexps.html#replace-replaceAll)

* [`Promise.any()`](https://exploringjs.com/impatient-js/ch_promises.html#Promise.any) 

* WeakRefs

* [Logical assignment operators](https://exploringjs.com/impatient-js/ch_operators.html#logical-assignment-operators)

* Underscores (`_`) as separators in [number literals](https://exploringjs.com/impatient-js/ch_numbers.html#numeric-separator-number-literals) and [bigint literals](https://exploringjs.com/impatient-js/ch_bigints.html#numeric-separator-bigint-literals)

  

# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

> '<picture>'：picture 元素
>
> **HTML `<picture>` 元素**通过包含零或多个 [``source](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/source) 元素和一个 [img``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img) 元素来为不同的显示/设备场景提供图像版本。浏览器会选择最匹配的子 `<source>` 元素，如果没有匹配的，就选择 `<img>` 元素的 [`src`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/img#attr-src) 属性中的URL。然后，所选图像呈现在<img>元素占据的空间中。

```html
<picture>
    <source srcset="/media/cc0-images/surfer-240-200.jpg"
            media="(min-width: 800px)">
    <img src="/media/cc0-images/painted-hand-298-332.jpg" alt="" />
</picture>

```

要决定加载哪个URL，[user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) 检查每个 `<source>` 的 [`srcset`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/source#attr-srcset)、[`media`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/source#attr-media) 和 [`type`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/source#attr-type) 属性，来选择最匹配页面当前布局、显示设备特征等的兼容图像。



# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

[重学数据结构与算法](https://bigfacemaster.cn/2021/03/13/Thinking/Relearn-Data-Structure-and-Algorithm/)
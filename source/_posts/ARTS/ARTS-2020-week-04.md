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

[Why Tailwind Isn't for Me](https://dev.to/jaredcwhite/why-tailwind-isn-t-for-me-5c90)

作者从几个方面说明了为什么Tailwind不适合他

1.  Tailwind promotes ugly-ass HTML.：这个是实话，让 **HTML** 没有那么优雅了。
2.  `@apply` is fundamentally incompatible and non-standard (and largely unnecessary).：不兼容和不标准是致命的问题。
3. Tailwind's focus on design systems and tokens could mostly be replaced by CSS Custom Properties (aka variables)—which IS a standard.：自定义程度不够
4. Tailwind forgets that web components exist. 现在[MDN](https://developer.mozilla.org/zh-CN/docs/Web/Web_Components)已经给出了标准的web component规范了。
5.  Finally, Tailwind encourages div/span-tag soup: Tailwind大量依赖 **div span**,限制了自定义**tag**的创建和使用。

这是一个百花齐放的互联网，会有各种各样的框架，没有最好的，只有最适合自己和业务的。同时 **React ** 也在开始尝试 **原子化 CSS** 或许未来会有更适合现代 **CSS** 以及现代前端、现代互联网的框架和技术。

# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

```tsx
try {
  // 正常的返回结果
} catch (e) {
  // 服务器错误
}
```

在最近的开发中，发现在服务器返回的错误结果中，**await promise**并没有捕获到错误，不知是通用的**request**中的错误，还是其他的。

所以还是采用 **try {} catch() {} ** 来完成异常的捕获，避免对用户造成不佳体验。



# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

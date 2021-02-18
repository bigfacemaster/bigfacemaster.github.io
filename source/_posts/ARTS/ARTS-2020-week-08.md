---
title: ARTS-2020-week-08
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
date: 2021-02-17 21:51:10
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

## [剑指 Offer 17. 打印从1到最大的n位数](https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/)

输入数字 `n`，按顺序打印出从 1 到最大的 n 位十进制数。比如输入 3，则打印出 1、2、3 一直到最大的 3 位数 999。

```javascript
const printNumbers = function(n) {
  const last = Math.pow(10, n);
  const res = [];
  for(let i = 1; i < last; i++) {
    res.push(i);
  }
  return res;
};
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

## [front-of-the-front-end and back-of-the-front-end web development](https://bradfrost.com/blog/post/front-of-the-front-end-and-back-of-the-front-end-web-development/)

### [full-stack developers](https://bradfrost.com/blog/post/full-stack-developers/)

简单的分析了前端后端的一些职能。

## front-of-the-front-end developer

A definition: **A front-of-the-front-end developer is a web developer who specializes in writing HTML, CSS, and presentational JavaScript code.**

- **Crafting semantic HTML markup** with a strong focus on accessibility, in order to make experiences that are friendly to browsers, assistive technologies, search engines, and other environments that can consume HTML.

- **Creating CSS code** that control the look and feel of the web experience, tackling colors, typography, responsive layout, animation, and any other visual aspect of the UI. Front-end designers architect resilient CSS code with a focus on modularity, flexibility, compatibility, and extensibility.

- **Authoring JavaScript that primarily manipulates objects in the DOM**, such as making an accordion panel open or close when you click the accordion title, or closing a modal window.

- **Testing across browsers and devices** to ensure the UI is functional and good-looking on a never-ending stream of desktops, mobile phones, tablets, and all manner of other web-enabled devices (and even [anticipating ones that haven’t been invented yet](http://bradfrost.com/blog/post/future-friendly-fruition/)!)

- **Optimizing the performance of front-end code** in order to create lightweight, fast-loading, snappy, [jank](http://jankfree.org/)-free experiences.

- **Working with designers** to ensure the brand, design vision, and UX best practices are properly translated into the browser, which, to remind you, is the actual place actual people will go to use the actual product.

- **Working with back-of-the-front-end developers** to ensure the front-end code is compatible with back-end code, services, APIs, and other technology architecture.

- **Creating a library of presentational UI components** authored in a templating language are packaged up to be consumed by other developers.

- **Authoring and documenting a robust, intuitive component API for each presentational component** so developers consuming the component can easily plug whatever they need into to it.

- **Writing unit tests for the presentational UI component library** code to ensure the components look and function properly.

- **Architecting the flexibility/composibility of the component library**, working with developers to understand how open/composable or rigid/locked down each component should be.

- **Maintaining the presentational components as a product,** meaning handling versioning, deploying, governance, release notes and all the operational stuff goes into maintaining a software product.

  ## back-of-the-front-end developers

  A definition: **A back-of-the-front-end developer is a web developer who specializes in writing \**JavaScript\** code necessary to make a web application function properly.**

  - **Writing application business logic** to handle things like [CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) functionality and to control application state, routing, cache, authentication, and so on. In short, back-of-the-front-end developers write the code necessary for the application to function properly.

  - **Wiring up, integrating with, and even authoring data sources, services, and APIs**. This can include things like retrieving, manipulating, and displaying content from a CMS, or posting data to the appropriate service when a user submits a form.

  - **Consuming the UI code** authored by the front-of-the-front-end developers in order to compose screens and connect real functionality data, and services.

  - **Optimizing the performance of JavaScript code** in order to create a snappy, responsive application that fetches and fetches/posts data quickly.

  - **Writing end-to-end, integration, and other tests** to ensure the application works as intended.

  - **Architecting and managing JavaScript-based infrastructure**, such as Node frameworks, tools, and services.

  - **Managing devops stuff**, such as JavaScript bundlers, deployment tooling, [CI/CD](https://en.wikipedia.org/wiki/CI/CD) stuff, and so on.

  - **Working with front-of-the-front-end developers** to ensure the UI component library contains all the components, variants, and API hooks necessary in order to build the application and all its states.

  - **Working with the product team** to ensure all product states are accurately represented in the living, breathing application

  - **Working with other backend developers and IT** to ensure the right technical infrastructure is in place and that the application is able to properly integrate/communicate with non-JavaScript backend code.

    > 其实前端现在还是要了解后端的一些机制，后端也要了解一些前端的机制，这样才能更好的理解彼此的工作，造成不必要的误解。
    >
    > 从我的角度来说，全栈是一个趋势：**偏向前端与偏向后端的全栈**，毕竟术业有专攻，了解其他，增加自己的广度，打磨自己的深度，这样才能有更广阔的眼界，能够创造出更好的工具。


# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

暂无，毕竟春节懈怠了。

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

暂无，毕竟春节懈怠了。
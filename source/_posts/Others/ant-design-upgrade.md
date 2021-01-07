---
layout: ant
title: ant design v3 升级到 ant design v4
date: 2021-01-05 18:10:34
tags: [antd]
---

> 背景：因新项目的开展，采用antd v4 && umi v3 && typescript，而另一个项目采用的是antd v3 && umi v2 && jsx。因为要同时兼顾两个项目，方便维护以及快速开发，将其升级到与新项目相同的技术栈与版本。

## ant design 的升级

根据 [官方文档](https://ant.design/docs/react/migration-v4-cn) 采用官方推荐的命令与工具进行一键升级

```shell
# 通过 npx 直接运行
npx -p @ant-design/codemod-v4 antd4-codemod src

# 或者全局安装
# 使用 npm
npm i -g @ant-design/codemod-v4
# 或者使用 yarn
yarn global add @ant-design/codemod-v4

# 运行
antd4-codemod src
```

首先根据命令行提示的各种`warning` && `error`进行修改。

完成之后，运行项目，会发现一些工具无法修改到的地方，逐步修改。

> 在项目升级的过程中，遇到的一个比较容易忽略的问题就是，Table 的 dataIndex 的多层级引用，从 `xxx.yyy` 变更为了 `['xxx', 'yyy']`

End, commit and push.

## umi 升级
同样是根据 [官方文档](https://umijs.org/docs/upgrade-to-umi-3) 可以快速升级

## jsx to tsx

 其实最初想要升级成`tsx`的主要原因是在`github trending`中看到 [Airbnb ts-migrate](https://github.com/airbnb/ts-migrate) 工具，其介绍为：**A tool to help migrate JavaScript code quickly and conveniently to TypeScript**。啊？这不是我刚好想要的么？

于是根据官方文档进行了升级，整个升级过程非常丝滑，最后按照自己的**lint**规则处理一下就能够满足大致的需求，剩下的就是进行新业务的开发以及相关功能的逐步重构。


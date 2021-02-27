---
title: 前端测试
date: 2021-02-27 22:36:51
tags:
  - Front
---

# 前端测试

前言：最近项目根据需求需要加入测试，主要是组件的测试，hooks测试，以及e2e测试。

因为我们的技术框架采用的是**React + Ant-Design-Pro + Umi**，所以我们采用采用了**Umi**生态链。

## Jest

因为**Umi**内置了jest作为测试方案。

Jest 是基于Node环境中的。所以主要用于测试逻辑和行为。

## React测试

采用**React-testing-library**来测试组件的行为和预期的输出。并且也是react官方推荐的测试框架。可完成单元测试+集成测试+e2e测试。可以与jest-dom一起使用，方便断言测试。

## react-hooks测试

采用的是@testing-library/react-hooks与react-testing-library一脉相承，所以采用其来作自定义hooks的测试是比较好的一个方案。

## e2e测试

End to End 端到端测试。模拟用户的行为，从开始到某个行为结束。需要测试参数，参数类型。参数值、参数数量、返回值、抛出错误等，目的在于保证特定函数能够在任何情况下都能够稳定可靠完成。单元测试只需要保证函数正常工作就OK了。



puppeteer是ant-design-pro已经集成好了的一个e2e测试框架。

cypress也是一个很好的e2e测试框架。



## 方案

Jest + @testing-library/react + @testing-library/react-hooks + puppeteer

or

Jest + @testing-library/react + @testing-library/react-hooks + cypress
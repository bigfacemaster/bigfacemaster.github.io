---
title: ARTS-2020-week-05
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
date: 2021-01-25 09:54:04
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

## [寻找数组的中心索引](https://leetcode-cn.com/problems/find-pivot-index/)

给定一个整数类型的数组 nums，请编写一个能够返回数组 “中心索引” 的方法。

我们是这样定义数组 中心索引 的：数组中心索引的左侧所有元素相加的和等于右侧所有元素相加的和。

如果数组不存在中心索引，那么我们应该返回 -1。如果数组有多个中心索引，那么我们应该返回最靠近左边的那一个。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/find-pivot-index
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



```tsx
const pivotIndex = (nums) => {
  if(!nums || nums.length === 0) {
    return -1;
  }
  const arrTotal = nums.reduce((a, b) => a + b);
  
  let sum = 0;
  
  for(let i = 0; i < nums.length ; i++) {
    const v = nums[i];
    if(sum * 2 + v === arrTotal) {
      return i;
    }
    sum += v;
  }

  return -1;
};
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

[How We Build Micro Frontends](https://blog.bitsrc.io/how-we-build-micro-front-ends-d3eeeac0acfc)

主要介绍了[bit](https://bit.dev/) 的微前端技术方案。

微前端的话采用过的是[umi/qiankun](https://qiankun.umijs.org/) 这个技术方案。因为我们采用的是**React + antd + umi **整套体系，所以实现起来很方便。文档还是蛮全的，而且实现上基本上属于无缝衔接。

如果技术栈是这么一套体系的，真的推荐[umi/qiankun](https://qiankun.umijs.org/) 。

# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

## [react-use](https://github.com/streamich/react-use)

在使用**react-use useAsyncFn**的时候，发现了这样一个问题。

![image-20210129154523325](http://bigfacemaster.test.upcdn.net/uPic/image-20210129154523325.png)

其原因是，接口反馈过慢，在反复切换页面的时候发现了此问题。

解决的方式就是在**useAsyncFn**中加入**deps**来控制。

```tsx
const [{ loading, value: data }, fetchData] = useAsyncFn(async() => {
  const { result } = await fetchServerData(params: any);
  return result ?? {};
}, [window.location.pathname])
```



# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

[ECharts graph 类型的图表绘制](https://bigfacemaster.cn/2021/01/29/Tools/EChartsGraph/)
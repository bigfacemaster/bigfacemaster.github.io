---

title: ARTS-2020-week-03.md
tags: [ARTS, Algorithm, Review, Tip, Share, 算法, 阅读, 技巧, 分享]
category: [ARTS, Algorithm, Review, Tip, Share, 算法, 阅读, 技巧, 分享]
date: 2021-01-016 14:36:18
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

# [实现 strStr()](https://leetcode-cn.com/problems/implement-strstr/)

实现 strStr() 函数。

给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/implement-strstr
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



```tsx
const strStr = (haystack, needle) {
  return haystack.indexOf(needle);
}
```



# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

[How much math you need for programming](https://lispmachine.wordpress.com/2014/12/05/how-much-math-you-need-for-programming/)

其中有一句比较喜欢：As computer programmers, we write programs, but why? We write programs to solve problems of this world. That is what computer programmers do, they solve problems. 程序所做的事情就是为了解决问题。

how tho world solved its problems in beginning:

![problem](https://lispmachine.files.wordpress.com/2014/12/math-1.jpg)

Then came Math and this is what most mathematicians did:

![https://lispmachine.files.wordpress.com/2014/12/math-2.jpg](https://lispmachine.files.wordpress.com/2014/12/math-2.jpg)

And this what almost all computer-programmers/software-engineers/developers do:

![https://lispmachine.files.wordpress.com/2014/12/math-3.jpg](https://lispmachine.files.wordpress.com/2014/12/math-3.jpg)



![https://lispmachine.files.wordpress.com/2014/12/math-4.jpg](https://lispmachine.files.wordpress.com/2014/12/math-4.jpg)

程序员的主要目的就是为了写出更好的代码，找到更好方式来创建软件，所以需要学好设计模式

Math is the most widely used vehicle to understand the nature and solve problems of this world. We can learn more ways of solving problems by learning mathematical methods.

once you understand Math then you can look at the problem and see whether it a probability problem, calculus problem or statistical problem etc. Math is related to the nature of the problem, not nature of software, software has its own methods and tools of solving problems, keep that in mind.

数学在各方面都有存在。

数学可以训练思维，更快更直接的解决程序问题。

所以数学很重要，不管怎么样都需要学好数学，尤其是其思维模式。我还记得有一句话说的是：很多学科的尽头就是物理，物理的尽头是数学，数学的尽头是哲学。

# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

> useMemo

该**API**属于**React Hooks**

```tsx
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

返回值为一个**memoized**的值；

传入依赖数组，如果依赖数组有变化，将会触发函数。

`memo`是在`DOM`更新前触发的

类比生命周期就是[shouldComponentUpdate](https://links.jianshu.com/go?to=https%3A%2F%2Fzh-hans.reactjs.org%2Fdocs%2Fhooks-faq.html%23how-do-lifecycle-methods-correspond-to-hooks)



# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

[封装[ECharts Next For React]](https://mp.weixin.qq.com/s/PNFE0FEnqIL59oE9-A5yOQ)

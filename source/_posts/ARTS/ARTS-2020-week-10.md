---

title: ARTS-2020-week-10
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
date: 2021-02-27 13:14:11
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

## [剑指 Offer 21. 调整数组顺序使奇数位于偶数前面](https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/)

输入一个整数数组，实现一个函数来调整该数组中数字的顺序，使得所有奇数位于数组的前半部分，所有偶数位于数组的后半部分。



```js
const exchange = function(nums) {
  const odds = nums.filter(v => v % 2 === 1);
  const evens = nums.filter(v => v % 2 === 0);
  return [...odds, ...evens];
};
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

[Why is esbuild fast?](https://esbuild.github.io/faq/#why-is-esbuild-fast)

原因:

> * 使用Go语言编写，而不是js(It's written in [Go](https://golang.org/) and compiles to native code.)：go 并行处理任务，js单线程。go线程共享内存，js线程序列化。垃圾回收机制，go堆栈共享，js单独回收。
> * 大量使用并行(Parallelism is used heavily.)：充分使用cpu资源
> * 一切从头编写(Everything in esbuild is written from scratch.)：不依赖于第三方库，可以从头设计并考虑性能。
> * 内存使用效率(Memory is used efficiently.)：最大时间复杂度：O(n);充分利用CPU和内存。

构建速度快；

# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

## Array.prototype.flat() && Array.prototype.flatMap() && Array.prototype.flatEach()

1. Array.prototype.flat()

   `**flat([depth])**` 方法会按照一个可指定的深度递归遍历数组，并将所有元素与遍历到的子数组中的元素合并为一个新数组返回。depth: 可选，指定要提取嵌套数组的结构深度，默认值为 1。一个包含将数组与子数组中所有元素的**新数组**。

   ```
   使用 Infinity，可展开任意深度的嵌套数组
   ```

   ```js
   const arr1 = [0, 1, 2, [3, 4]];
   
   console.log(arr1.flat());
   // expected output: [0, 1, 2, 3, 4]
   
   const arr2 = [0, 1, 2, [[[3, 4]]]];
   
   console.log(arr2.flat(2));
   // expected output: [0, 1, 2, [3, 4]]
   ```

   

2. Array.prototype.flatMap()

   `**flatMap()**` 方法首先使用映射函数映射每个元素，然后将结果压缩成一个**新数组**。它与 [map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) 连着深度值为1的 [flat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/flat) 几乎相同，但 `flatMap` 通常在合并成一种方法的效率稍微高一些。返回**新数组**。

   ```
   var new_array = arr.flatMap(function callback(currentValue[, index[, array]]) {
       // return element for new_array
   }[, thisArg])
   callback
   可以生成一个新数组中的元素的函数，可以传入三个参数：
   currentValue
   当前正在数组中处理的元素
   index可选
   可选的。数组中正在处理的当前元素的索引。
   array可选
   可选的。被调用的 map 数组
   thisArg可选
   可选的。执行 callback 函数时 使用的this 值。
   
   ```

3. Array.prototype.flatEach()

   `**forEach()**` 方法对数组的每个元素执行一次给定的函数。返回**undefined**

   ```
   arr.forEach(callback(currentValue [, index [, array]])[, thisArg])
   callback
   为数组中每个元素执行的函数，该函数接收一至三个参数：
   currentValue
   数组中正在处理的当前元素。
   index 可选
   数组中正在处理的当前元素的索引。
   array 可选
   forEach() 方法正在操作的数组。
   thisArg 可选
   可选参数。当执行回调函数 callback 时，用作 this 的值。
   
   
   ```

# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

[关于读书](https://bigfacemaster.cn/2021/03/06/Thinking/About-Reading/)
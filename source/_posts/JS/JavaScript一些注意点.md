---
title: JavaScript一些注意点
date: 2016-12-22 18:21:08
tags: [JavaScript, JS]
category: code
---

# 变量声明提前 ( var hoisting)
由于变量声明总是在*任意代码执行之前处理的*，所以在代码中的任意位置声明变量总是等效于在代码开头声明，说明，变量可以再声明之前使用，这就是声明提前(hoisting)；
```
a = 2;
var a;
==>
var a ;
a = 2;
```
# let
let 声明了贵块级域的局部变量，，并且可以给他一个初始值；同时把变量的作用域限制在块级域当中，其作用域包含定义它的块以及任何包含的子块中。var 则是全局或者函数级。</br>
Attention:
* 在同一个函数或同一个作用域中用let重复定义一个变量将引起TypeError；
# const
创建一个只读的常量，只能赋值一次。
# 数据结构和类型
## 六种原型数据类型
* Boolean，布尔值，true && flase；
* null，一个表明null值的特殊关键字，JavaScript是大小写敏感的，null与Null和NULL或其他的变量完全不同；
* undefined，变量未定义时的属性；
* Number，表示数字；
* String，表示字符串；
* Symbol，一种数据类型，他的实例是唯一且不可改变的。
## Object对象

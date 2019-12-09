---
title: 前端规范-JavaScript篇
date: 2016-12-12 01:04:04
tags: 前端规范
category: code
---
# 通用约定
## 注释
### 原则
As short as possible：如果不是非要不要注释，必须注释，比如函数功能，参数传入说明，etc，提高代码本身的清晰度与可读性；<br/>
As long as necessary: 必须严格的将注释写清楚；
### 单行注释
必须独占一行。 // 后面加上一个空格，其缩进方式以下一行被说明的对象保持一直。
### 多行注释
采用多个单行注释构成 //
### 函数/方法注释
- 函数/方法注释必须包含函数说明，有参数和返回值时必须使用注释标识；
- 参数和方绘制必须包含类型信息和说明；
- 当函数是内部函数，外部不可访问时，可以使用@inner标识；
```
/**
* 函数描述
* 作用
* 名称
* @param {string} p1 参数1的说明
* @return {Object} 返回值描述
*/
function example( a, b, c) {
  var ...;
  return ....
}
```
### 命名规范
类命：使用名称;</br>
函数名： 使用动宾短语；</br>
boolean类型的变量使用is或has开头；</br>
Promise 对象用动宾短语的进行时表达：var  gettingCanvas = ....；
### 接口命名规范
1. 可读性，见名知义；
2. 不要与采用的框架冲突；
3. 尽量写完全，不要采用缩写；
### True && False 布尔表达式
类型检测优先使用 typeof,对象类型检测使用instanceof。
### 不要在Array上使用 for-in 循环
for-in 循环只用于 ```object/map/hash/``` 的遍历，对 ```Array``` 用for-in循环有时会出错，并不是从0 ---- length - 1；进行遍历，而是所有出现在对象及其原型链的键值；
### 二元和三元操作符
操作符始终写在前一行，以免分号的隐式插入产生预想不到的问题；
```
var x = a ? b : c;
var test = test1 ?
           test2 : test3;
```
### 条件(三元)操作符 (?:)
三元操作符用于替代if条件判断语句。
```
return var ? function1() : function2();
```
### && 和 ||
二元布尔操作符是可以短路的，只有在必要时才会计算到最后一项；
```
function test( param) {
  var params = param || window;
}
```

## jQuery 规范
### jQuery Variables
* 存放jQuery对象的变量以```$```开头；
2. 将jQuery选择器返回的对象缓存到本地变量中反复使用；
3. 使用驼峰法命名变量(ex:id);
```
var $map = $("#myMap");
$map.bind();
```
### Selectors

1. 尽可能的使用id选择器，因为调用的是浏览器原生的方法 document.getElementById,提高性能；id具有唯一的标识性；
2. 在父元素中选子元素使用```.find()```方法性能较好；
```
var $result = $("#parentId").find(".child");
```
### DOM Manipulation
1. 操作DOM元素的时候，尽量将其分离节点，操作结束后，再插入节点；
2. 使用字符串连接或```array.join```要比```.append()```性能好；
```
var $content = $("#content");
$content += "<div>" + text + "</div>";
```
### Events
1. 如果需要，对事件使用自定义的 ```namespace```这样容易解绑特定的事件，而不会影响到对此元素的其他事件的监听；
2. 对Ajax加载的DOM元素绑定事件时尽量使用事件委托。事件委托允许在父元素绑定事件，子代元素可以可以响应事件，也包括Ajax加载后子代元素；
```
$("#testClick").on("click", eventFunction() {});
$("#testClick").unbind("click");
$("#childClick").on("click","button", eventFunction() {});
```
### 链式写法
1. 尽量采用链式写法而不是用变量缓存或者多次调用选择器方法；
2. 当链式写法超过三个Or事件绑定变得复杂后，使用换行和缩进保存代码的可读性；
```
$("#ex").attr("flag", "edit").show();
$("#ex").attr("flag", "edit")
        .on("click",funciton(){})
        .on("mouseover", function(){})
        .show();
```
### Miscellaneous 混合型
1. 多个参数使用对象字面量存储；
2. 不要将CSS写在jQuery里面；
3.正则表达式最只使用.test() && .exec().尽量避免"string".match();
## 性能优化
### 避免不必要的DOM操作
浏览器遍历DOM元素对性能有很大影响。最好的方便就是一个元素需要多次使用的时候，将其保存在一个变量中，可以避免多次查询DOM树了。</br>
谨记：能够在HTML中完成的就一定要在HTML完成，能够在CSS中完成的一定要在CSS中完成。
### 缓存数组长度
将数组的长度存在一个变量当中，可以避免每次循环的时候都去重新计算数组的长度；
### 异步加载第三方内容
### 避免使用jQuery实现动画
* 禁止使用 slideUp/Down, fadeIn/fadeOut等方法；
* 尽量不适用animate() 方法；
*















# 参考极客学院前端规范指南

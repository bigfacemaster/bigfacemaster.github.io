---
title: Ajax
date: 2016-12-16 13:03:57
tags: ["Ajax", "jQuery Ajax"]
category: Code
---
Ajax的全称为：Asynchronous JavaScript and XML, 主要用于与服务器之间的交互；其使用XHTML呈现内容，CSS处理表现，使用文档对象模型（DOM）和JavaScript显示动态内容。</br>
Ajax基于，使用HTML和层叠样式表（CSS）基于浏览器呈现；数据存储在XML各种并且需要从服务器获取；在浏览器中使用XMLHttpRequest从服务器获取数据；使用JavaScript来对返回的数据进行操作；
# Ajax操作步骤
* 一个触发的事件；
* 创建一个XMLHttpRequest对象；
* 配置XMLHttpRequest对象；
* 使用XMLHttpRequest对象创建一个到Web服务器的异步请求；
* Web服务器返回包含XML文档的结果；
* XMLHttpRequest对象调用callback()函数处理结束；
* 更新HTML DOM
## 事件触发
JavaScript 函数作为事件结果被调用；
## 创建XMLHttpRequest对象
```JavaScript
var xmlHttp;
if (typeof XMLHttpRequest != "undefined") {
    xmlHttp = new XMLHttpRequest();
} else if (window.ActiveXObject) {
    var aVersions = ["Msxml2.XMLHttp.5.0", "Msxml2.XMLHttp.4.0",
        "Msxml2.XMLHttp.3.0", "Msxml2.XMLHttp", "Microsoft.XMLHttp"];
    for (var i = 0; i < aVersions.length; i++) {
        try {
            xmlHttp = new ActiveXObject(aVersions[i]);
            break;
        } catch (e) {}
    }
}
```
## 属性和方法
```JavaScript
abort() ==> 请求取消;
getAllResponseHeader() ==> 获取响应的所有Http头;
getResponseHeader() ==> 获取指定的Http头
open( method, url) ==> 创建请求， method请求类型 get/post
send( ) ==> 发送请求
setRequestHeader() ==> 指定请求的Http头
onreadystatechange ==> 发生任何状态变化时的事件控制对象（帮顶一个事件处理函数）
readyState ==> 请求的状态
                  0  尚未初始化
                  1  正在发送请求
                  2  请求完成
                  3  请求成功
                  4  数据接收成功
responseText ==> 服务器返回的文本
responseXML ==> 服务器返回的xml，可以当作DOM处理
status  ==> 服务器返回的http请求响应值常用的有：
                200 表示请求成功
                202 请求被接受但处理未完成
                400 错误的请求
                404 资源未找到
                500 内部服务器错误
```

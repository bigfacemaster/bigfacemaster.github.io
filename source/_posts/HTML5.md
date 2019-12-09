---
title: HTML5
date: 2018-03-04 16:43:24
tags: HTML
category: 前端
---

# HTML5

## 语义

### HTML5中的节段和提纲

```javascript
<section>, <article>, <nav>, <header>, <footer>, <aside>, <hgroup>
```

### 使用HTML5的音频和视频

```javascript
<audio> && <video> 元素嵌入和允许操作新的多媒体内容。
```

### HTML5的表单

```javascript
强制验证API，一些新的属性， <input> 属性type的一些新值，新的<output>元素。
```

### 新的语义元素

```javascript
<mark>, <figure>, <figcaption>, <data>, <time>, <output>, <progress>, <meter>, <main>
```

### <iframe>的改进

```javascript
使用sandbox，seamless 和 srcdoc 属性
```

### MathML

```javascript
允许直接嵌入数学公式
```

## 通信

### Web Sockets

```javascript
允许在页面和服务器之间建立持久连续并通过这个方式来交换非HTMl数据
```

### Server-sent events

```javascript
允许服务器向客户端推送事件，而不是仅在响应客户端请求时服务器才能发送数据的传统范式。
```

### WebRTC

```javascript
RTC代表：即使通信，允许连接到其他人，直接在浏览器中控制视频会议，而不需要一个插件或是外部的应用程序
```

## 离线&&存储

### 离线资源： 应用程序缓存

```javascript
HTML5离线资源规范
```

### 在线和离线事件

```javascript
让应用程序和扩展检测是否存在可用的网络连接，以及在连接建立和断开时能感知到。
```

### WHATWG 客户端会话和持久化存储（DOM存储）

```javascript
客户端会话和持久化存储让web应用程序能够在客户端存储结构话数据
```

### IndexedDB

```javascript
是一个为了能够在浏览器存储大量结构化数据，并且能够在这些数据上使用索引进行高性能检索的Web标准
```

### 自Web应用程序中使用文件

```javascript
文件的API，从而使Web应用程序可以访问由用户选择的本地文件，包括使用 type file的<input> 元素的 multiple属性针对多文件选择的支持，还有FileReader。
```

## 多媒体

### 使用HTML5音视频

```javascript
<audio> && <video> 元素前乳并支持新的多媒体内容的操作。
```

### WebRTC

```javascript
RTC: 即时通信，允许连接到其他人，在浏览器中直接控制视频会议，而不需要一个插件或是外部的应用程序
```

### 使用 Camera API

```javascript
允许使用，操作计算机摄像头，并从中存储图像
```

### Track && WebVTT

```javascript
<track> 元素支持字幕和章节。
```

## 3D， 图像 & 效果

### Canvas教程

```javascript
绘制图像
```

### WebGL

```javascript
WebGL通过引入一套非常符合OpenGL ES2.0 并可以用在HTML5<canvas>元素的API给Web带来3D
```

### SVG

```javascript
一个基于XML的可以直接嵌入到HTML中的矢量图像格式。
```

### 性能 & 集成

### Web Workders

```javascript
能够把JavaScript计算委托给后台线程，通过允许这些活动以防止使交互型事件变得缓慢
```

### XMLHttpRequest Level2

```javascript
允许异步读取页面的某些部分，允许其显示动态内容，根据时间和用户行为而有所不同。Ajax
```

### 即时编译的JavaScript引擎

```
新一代的JavaScript引擎功能更强大
```

### History API

```
允许对浏览器历史记录进行操作
```

### contentEditable属性：把你的网站改编成wiki

```

```

### 拖放

```javascript
HTML5的拖放API能够支持在网站内部和网站之间拖放项目。
```

### HTML中的焦点管理

```javascript
支持新的HTML5 activeElement和hasFocus属性
```

### 基于Web的协议处理程序

```javascript
navigator.registerProtocolHandler() 方法把Web应用程序注册成一个协议处理程序。
```

### requestAnimationFrame

```javascript
允许控制动画渲染以获得更优性能
```

### 全屏API

```javascript
为一个网页或者应用程序控制使用整个屏幕，而不是现实浏览器界面
```

### 指针锁定API

```javascript
允许锁定到内容的指针，这样游戏或者类似的应用程序在指针到达窗口限制时也不会失去焦点
```

### 在线和离线事件

```javascript
为了构建一个良好的具有离线功能的 web 应用程序，你需要知道什么时候你的应用程序确实离线了。顺便提一句，在你的应用程序又再回到在线状态时你也需要知道
```

## 设备访问

### 使用 Camera API

```javascript
允许使用和操作计算机的摄像头，并从中存取照片
```

### 触控事件

```javascript
对用户按下触控屏的事件作出反应的处理程序
```

### 使用地理位置定位

```javascript
让浏览器使用地理位置服务定位用户的位置
```

### 检测设备方向

```javascript
让用户在运行浏览器的设备变更方向时能够得到信息。这可以被用作一种输入设备（例如制作能够对设备位置做出反应的游戏）或者使页面的布局跟屏幕的方向相适应（横向或纵向）
```

### 指针锁定 API

```javascript
允许锁定到内容的指针，这样游戏或者类似的应用程序在指针到达窗口限制时也不会失去焦点
```

## 样式

### 新的背景样式特性

```javascript
box-shadow给逻辑框设置一个阴影，而且还可以设置多背景
```

### 更精美的边框

```javascript
现在不仅可以使用图像来格式化边框，使用 border-image 和它关联的普通属性，而且可以通过 border-radius 属性来支持圆角边框。
```

### 为你的样式设置动画

```javascript
CSS Transitions 以在不同的状态间设置动画，或者使用CSS Animations在页面的某些部分设置动画而不需要一个触发事件
```

### 排版方面的改进

```javascript
text-overflow hyphenation 阴影 
```

### 新的展示性布局

```javascript
CSS多栏布局 && CSS灵活方框布局
```


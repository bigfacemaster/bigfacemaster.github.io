---
title: 前端规范-HTML篇
date: 2016-12-07 21:42:16
tags: 前端规范
category: code
---
# 基本原则
A、结构(HTML)、样式(CSS)、行为分离(JavaScript): 尽量保证HTML文件只有HMTL，CSS文件只有样式表，JavaScript文件放到单独的JavaScrip脚本中；<br/>
B、缩进：统一使用相同的缩进，两个空格或者四个，不要使用Tab或者Tab与空格混合，不同的编辑器对Tab的定义不同；<br/>
C、文件编码：编码格式统一采用UTF-8进行编码；<br/>
D、一律采用小写字母；<br/>
E、省略外部资源链接URL中的http/https协议，使得URL成为相对地址，避免Mixed Content问题，减少文件字节数，其他的协议URL不省略；<br/>
F、统一注释规则；<br/>
G:代码验证(W3C HTML && CSS Validator);</br>

# HTML
** 在实用性的基础上尽量遵循HTML标准和语义 **
## 通用约定
### 标签
A、自闭和(self-closing)标签，无需闭合；<br/>
B、可选的闭合标签(closing tag), 需要闭合；<br/>
C、尽量减少标签数量；
### class && id
A、class应该以功能或者内容命名，不应以表现形式命名；<br/>
B、class与id单词字母小写，多个单词组成时，采用中划线“-”分隔，不推荐采用驼峰法，或者下划线 "_; </br>
C、使用唯一的id作为JavaScript hook， 同时避免创建无样式信息的class；</br>
### 属性顺序
HTML 属性应该按照特定的顺序出现保证易读性： id、class、name、data-xxx、（src、for、type、href）、(title、alt)、（aria-xxx、role）；
### 引号
属性的定义，统一采用双引号
### b嵌套
a标签中不允许嵌套div，a标签中也不允许嵌套a，语义嵌套规范；</br/>
#### 语气嵌套规范
A、li、用于ul、ol、中;<br/>
B、dd、dt用于dl中；<br/>
C、thead、tbody、tfoot、tr、td用于table中；
#### 严格嵌套规范
A、inline-level元素，只能包含文本或者其他的inline-level元素;<br/>
B、a标签里面不可以嵌套交互式元素a、button、select、etc.;<br/>
C、p标签里面不可以嵌套块级元素div、h1~h6、ul、ol、li、dl、dd、dt、form，etc.;
#### 布尔值属性
在HTML5中，disabled/checked/selected/等属性不用设置值；
#### 语义化
p--> 段落；<br/>
h1~h6 --> 标题；<br/>
ul --> 无序列表；<br/>
ol --> 有序列表； <br/>
blockquote --> 大段引用； <br/>
cite --> 一般引用； <br/>
b --> 为样式加粗而加粗；<br/>
strong --> 为强调内容而加粗；<br/>
i --> 为样式倾斜而倾斜；<br/>
em --> 为了强调内容而倾斜；<br/>
code --> 代码标识；<br/>
abbr --> 缩写；
## HEAD
### 文档类型
统一采用HTML5文档类型标识:<br/>
<!DOCTYPE html>
### 语义属性
```
<html lang="zh-Hans"><br/>
<html lang="en">
```
### 字符编码
```
<html>
  <head>
    <meta charset="utf-8">
    ....
  </head>
  <body>
  </body>
</html>
```
### SEO 优化
```
<head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
  <!-- SEO -->
  <title>Style Guide</title>
  <meta name="keywords" content="your keywords">
  <meta name="description" content="your description">
  <meta name="author" content="author,email address">
</head>
```
### viewport
viewport: 指浏览器可视区域大小；<br/>
width: 浏览器宽度；<br/>
device-width: 设备分辨率宽度，输出设备的屏幕可见宽度；<br/>
initial-scale: 初始缩放比例；<br/>
maximum-scale: 最大缩放比例；<br/>
```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

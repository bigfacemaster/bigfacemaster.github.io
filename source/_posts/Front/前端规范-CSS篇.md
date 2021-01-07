---
title: 前端规范-CSS篇
date: 2016-12-08 12:30:03
tags: 前端规范
category: code
---
# 基本原则
## 代码组织
A、以组件为单位组织代码段；<br/>
B、制定一致的注释规范；<br/>
C、组件块和子组件块之间使用使用一空行分隔，子组件块之间三空行分隔；<br/>
D、如果使用了多个CSS文件，将其按照组件而非页面的形式分拆，因为页面会被重组，而组件只会被移动；<br/>
```
/* ==========================================================================
组件块
============================================================================ */
/* 子组件块
============================================================================ */
.selector {
padding: 15px;
margin-bottom: 15px;
}
/* 子组件块
============================================================================ */
.selector-secondary {
display: block; /* 注释*/
}
.selector-three {
display: span;
}
```
## Class &&  ID
A、使用语义化、通用的命名方式；<br/>
B、使用连字符“-”作为ID、Class名称界定符，不要使用驼峰法或者下划线；<br/>
C、避免选择器嵌套层级过多，尽量少于3级；<br/>
D、避免选择器和Class、ID叠加使用
## 声明块格式
A、选择器分组时，保持独立的选择器占用一行；<br/>
B、声明块的左括号 "{" 前添加一个空格；<br/>
C、声明块的右括号 "}" 应单独成行； <br/>
D、声明语句中的 ":" 后应添加一个空格；<br/>
E、声明语句应以分号 “；” 结尾； <br/>
F、一般以都好分隔的属性值，每个逗号后应添加一个空格;<br/>
G、rgb()，rgba()，hsl()，hsla()或者rect()括号内的值，逗号分隔，但逗号后不添加一个空格；<br/>
H、对于属性值或者颜色参数，省略小于1的小数前面的0( 0.5 --> .5);<br/>
I、十六进制应该全部小写和尽量简写；<br/>
J、避免为0制定单位；
## 声明顺序
相关属性为一组，Ex：<br/>
A、positioning<br/>
B、box model<br/>
C、typographic<br/>
D、visual<br/>
Cause: 定位positioning可以从正常的文档流中移除元素，并且能够覆盖盒子模型(box model)相关的样式，因此排在首位，盒子模型决定了组件的尺寸和位置，因此第二位；
## 媒体查询(media query)的位置
将媒体查询放在尽可能相关规则的附近，不推荐分开；
```
.element { ... }
.element-avatar { ... }
.element-selected { ... }
@media (max-width: 768px) {
.element { ...}
.element-avatar { ... }
.element-selected { ... }
}
```
## 避免使用@import
@import 速度较慢, 且会增加额外的请求数，还会导致不可预测的为题； <br/>
替换：<br/>
A、 使用多个元素；<br/>
B、 通过Sass或者Less类似的CSS预处理将多个CSS文件编译为一个文件； <br/>
C、 其他CSS文件合并工具；
## 链接样式顺序
```
a:link -> a:visited -> a:hover -> a:active(LoVeHAte)
```
## 无需添加浏览器厂商前缀
使用Autoprefixer自动添加浏览器厂商前缀，编写CSS时 不需要添加浏览器前缀，直接使用标准的CSS编写;
# 模块组织
组件化的目的在于有效的维护CSS；<br/>
### components(组件)
将每一个块功能都可以分割为一个独立的组件(components)
#### Naming components （组件命名）
components最少以两个淡出命名, 通过“-”分离；EX:.article-mould;
### Elements（元素）
Elements是components中的元素；
#### Naming Elements（元素命名）
Elements的类名应尽可能仅有一个单词；
```
.article-mould {
> .title {/*---*/}
> .content {/*---*/}
}
```
如果使用多个单词表示，则直接连接；
```
.article-mould {
> .contentimportant{/*------*/}
}
```
### Avoid tag selectors（避免使用标签选择器）
尽量都使用classname，这样表达明确，方便维护；
### variants (变体)
无论实在components中还是在Elements中都可能会出现variants；
#### Naming variants(变体命名)
variants的classname应带有前缀中划线"-"，Ex:
```
.color-button {
&.-red { /* ... */ }
&.-blue { /* ... */ }
&.-black { /* ... */ }
}
```
### Element variants(元素变体)
```
.article-mould {
  >.full{}
  >.middle{}
}
```
### Dash prefixes（中划线前缀）
A、避免歧义与Element;<br/>
B、CSS class仅能以单词或者“_”或者”-”开头；<br/>
C、中划线比下划线更容易输出；
### Layout（布局）
严格的按照父子类集合
### Avoid positioning properties（避免定位属性）
components应在不同的地方都是可以复用的，提高代码的使用效率,因此，通用的组件避免使用("positioning", "float", "margin", "width, height")
### Fixed dimensions（固定尺寸）
需要固定的尺寸一定使用固定的尺寸，避免图片变形；
### Define positioning in parents（在父元素中设置定位）
如果需要在组件中设置定位，应在组件的父元素中进行处理；

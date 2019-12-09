---
title: ESLint 简要说明
date: 2018-06-15 11:18:06
tags: ESLint
category: Tool
---

# ESLint 简要说明

## 配置
ESLint 具有高可配置性，这意味着你可以根据需求添加需要的代码检验规则，让它符合你的需求。ESLint 的配置方式可以有以下两种形式：

* 在注释中配置：使用 JavaScript 文件中使用注释包裹配置内容

* 在配置文件中配置：使用单独的文件来进行配置，这个文件可以是 JavaScript, JSON, YAML，文件名为 `.eslintrc.*` （添加文件类型的后缀），或者在 package.json 的 eslintConfig 字段进行配置，ESLint 会自动地去寻找这些配置文件，你也可以在命令行中指定配置文件。

## 解析器选项
ESLint 默认按照 ES5 的语法来解析，你可以在这里指定期望的 JavaScript 语法版本，在配置文件中可以使用 `parserOptions` 字段来配置：
```JavaScript
{
    "parserOptions": {
        "ecmaVersion": 6, // JavaScript 版本，3, 5 (default), 6 (2015), 7 (2016)
        "sourceType": "module", // "script" (default) 或者 "module"，说明你的代码是否是 ECMAScript 模块。
        "ecmaFeatures": { // 其他的一些语法特性的配置
            "jsx": true
        }
    }
```

## 解析器
指定语法解析器，ESLint 默认使用 Espree，你也可以指定其他的语法解析器，比如 [babel-eslint](https://www.npmjs.com/package/babel-eslint)

```javascript
{
    "parser": "babel-eslint"
}
```

## 环境
不同的环境可能有不同的全局变量，比如使用 amd 环境，就会有 require 和 define 两个函数。这里有详细的可选环境 [Specifying Environments](https://eslint.org/docs/user-guide/configuring#specifying-environments)，常见的环境有：
* browser
* node
* es6
* commonjs

```javascript
{
  "env" : {
    "browser": true,
    "node": true,
  }
}
```

一个工程中可能有不同的文件会运行在不同的环境下，这个时候可以在文件内使用注释来指定环境 `/* eslint-env node, mocha */`

## 插件
ESLint 支持使用第三方的插件，这些插件应该是使用 npm 安装的，插件的名字通常形如 `eslint-plugin-xxx`，在配置插件的时候可以忽略 `eslint-plugin-`

```javascript
{
    "plugins": [
        "plugin1",
        "eslint-plugin-plugin2"
    ]
}
```

## 规则

ESLint 包含大量的规则，你可以选择自己需要的规则进行配置，配置的方式如下：

```javascript
{
    "rules": {
        "eqeqeq": "off",
        "curly": "error",
        "quotes": ["error", "double"]
    }
}
```
每个规则可以取以下三类值：

* "off" or 0 - 关闭该规则
* "warn" or 1 - 违反该规则的时候给出警告
* "error" or 2 - 违反该规则的时候报错
有时候某个规则可能包含选项，比如代码缩进，你需要指定缩进的空格数，这个参数可以以这种方式传入：`"intend":["error", 4]`，即，使用括号将参数传进去，三个或四个参数依然使用这种方式传入，把参数都放在括号里就好了。

要想重新设置某个插件定义的 rule ，需要按如下方式设置：

```javascript
{
    "rules": {
        "react/self-closing-comp": 1,
        "react/wrap-multilines": 0
    }
}
```

## 使用注释关闭规则
在代码中可能有某些场景不得不违反某个规则，这个时候可以使用注释来针对性地关闭规则。

> 关闭某块代码的检验:

```javascript
/* eslint-disable */

alert('foo');

/* eslint-enable */

```

> 关闭代码块某些规则的检验

```javascript
/* eslint-disable no-alert, no-console */

alert('foo');
console.log('bar');

/* eslint-enable no-alert, no-console */
```

> 彻底关闭对某个文件的检验

```javascript
/* eslint-disable */

alert('foo');

```

> 关闭对某行代码的检验

```javascript
alert('foo'); // eslint-disable-line

// 或者

// eslint-disable-next-line
alert('foo');

```

## 配置文件的寻找和运用规则


子级的配置文件中的规则最优先，如果父级目录也就 eslint 的配置文件，其规则会追加进来。如果根目录下同时存在 eslintrc 以及 package.json 中的 eslintConfig 字段，会忽略 package.json 中的配置。

如果在 root 目录下存在一个 eslint 的配置文件，那么它只会在项目中没有找到任何配置文件的时候才会被应用。eslint 默认会不断向上寻找 eslintrc 知道根目录，你可以阻止它这么做通过在某个配置文件中写入 `"root": true`。

使用不同方式配置的配置信息有不同的优先级，具体表现为：

行内注释中的配置的优先级 > 通过命令行传入 > 配置文件

## 扩展配置文件
使用 `extends` 字段可以来扩展一些现有的配置文件，比如可以使用开源社区发布的一些可共享的配置文件包.

## More
[more](https://eslint.org/docs/)

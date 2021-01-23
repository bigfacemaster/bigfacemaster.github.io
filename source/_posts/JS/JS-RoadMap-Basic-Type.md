---

title: JS-RoadMap-Basic-Type
date: 2021-01-22 18:18:57
tags: [JS]
---
# JS 知识图谱之基本上类型

## 数据类型概念

>1. undefined
>2. Null
>3. Boolean
>4. String
>5. Number
>6. Symbol
>7. BigInt
>8. Object: Array、RegExp、Date、Math、Function

## 数据类型存储

>1. 基本类型存储在**栈内存**，被引用或拷贝时，会创建一个完全相等的变量；
>2. 引用类型存储在**堆内存**，存储的是地址，多一个引用指向同一个地址，这里会设计一个“共享”的概念。

## 数据类型检测

1. typeof

   ```tsx
   typeof 1 // 'number'
   typeof '1' // 'string'
   typeof undefined // 'undefined'
   typeof true // 'boolean'
   typeof Symbol() // 'symbol'
   typeof null // 'object'
   typeof [] // 'object'
   typeof {} // 'object'
   typeof console // 'object'
   typeof console.log // 'function'
   ```

2. instanceof

   ```tsx
   let Car = function() {}
   let benz = new Car()
   benz instanceof Car // true
   let car = new String('Mercedes Benz')
   car instanceof String // true
   let str = 'Covid-19'
   str instanceof String // false
   ```

   **instanceof**原理手写

   ```tsx
   const handleInstanceOf = (val, type) => {
     if(typeof val !== 'object' || val === null) {
       return false;
     }
     let proto = Object.getPrototypeOf(val);
     while(true) {
       if(proto === null) {
         return false;
       }
       if(proto === type.prototype) {
         return true;
       }
       proto = Object.getPrototypeOf(proto);
     }
   }
   
   console.log(handleInstanceOf(new String('Hello TS'), String)); // ture
   console.log(handleInstanceOf('Hello TS', String));  // false
   ```

   **instanceof** vs **typeof**

   >1. **instanceof**可以准确地判断复杂引用数据类型，但不能正确判断基本数据类型；
   >2. **typeof**可以判断基础数据类型，但是在引用数据类型中，除了**function**类型以外，其他的无法判断。

3. Object.prototype.toString

   **toString()**是**Object**的原型方法，调用此方法，返回的格式**“[object Type]”**的字符串，其中**Type**就是对象的类型。对于**Object**对象，直接使用**toString()**方法就可以放回**[object Object]**，其他类型的需要使用**call**来调用，才能返回正确的类型信息。

   ```tsx
   Object.prototype.toString({})       // "[object Object]"
   Object.prototype.toString.call({})  // "[object Object]"
   Object.prototype.toString.call(1)    // "[object Number]"
   Object.prototype.toString.call('1')  // "[object String]"
   Object.prototype.toString.call(true)  // "[object Boolean]"
   Object.prototype.toString.call(function(){})  // "[object Function]"
   Object.prototype.toString.call(null)   //"[object Null]"
   Object.prototype.toString.call(undefined) //"[object Undefined]"
   Object.prototype.toString.call(/123/g)    //"[object RegExp]"
   Object.prototype.toString.call(new Date()) //"[object Date]"
   Object.prototype.toString.call([])       //"[object Array]"
   Object.prototype.toString.call(document)  //"[object HTMLDocument]"
   Object.prototype.toString.call(window)   //"[object Window]"
   ```

   

   ```tsx
   const getType = (val) => {
     if(typeof val !== 'object') {
       return typeof val;
     }
     return Object.prototype.toString.call(val).replace(/^\[object (\S+)\]$/, '$1').toLowerCase();
   }
   console.log(getType([]));
   console.log(getType(123));
   console.log(getType(window))
   ```

   

# 类型转换

## 强制类型转换

 Number()、parseInt()、parseFloat()、toString()、String()、Boolean()

1.  Number()

   > 如果是布尔值，true 和 false 分别被转换为 1 和 0；
   >
   > 如果是数字，返回自身；
   >
   > 如果是 null，返回 0；
   >
   > 如果是 undefined，返回 NaN；
   >
   > 如果是字符串，遵循以下规则：如果字符串中只包含数字（或者是 0X / 0x 开头的十六进制数字字符串，允许包含正负号），则将其转换为十进制；如果字符串中包含有效的浮点格式，将其转换为浮点数值；如果是空字符串，将其转换为 0；如果不是以上格式的字符串，均返回 NaN；
   >
   > 如果是 Symbol，抛出错误；
   >
   > 如果是对象，并且部署了 [Symbol.toPrimitive] ，那么调用此方法，否则调用对象的 valueOf() 方法，然后依据前面的规则转换返回的值；如果转换的结果是 NaN ，则调用对象的 toString() 方法，再次依照前面的顺序转换返回对应的值（Object 转换规则会在下面细讲）。

2. parseInt()、

3. parseFloat()、

4. toString()、

5. String()、

6. Boolean()

   > 除了 undefined、 null、 false、 ''、 0（包括 +0，-0）、 NaN 转换出来是 false，其他都是 true。

   

   # 隐式类型转换

> 凡是通过逻辑运算符 (&&、 ||、 !)、运算符 (+、-、*、/)、关系操作符 (>、 <、 <= 、>=)、相等运算符 (==) 或者 if/while 条件的操作，如果遇到两个数据类型不一样的情况，都会出现隐式类型转换。

## '==' 的隐式类型转换规则

> 如果类型相同，无须进行类型转换；
>
> 如果其中一个操作值是 null 或者 undefined，那么另一个操作符必须为 null 或者 undefined，才会返回 true，否则都返回 false；
>
> 如果其中一个是 Symbol 类型，那么返回 false；
>
> 两个操作值如果为 string 和 number 类型，那么就会将字符串转换为 number；
>
> 如果一个操作值是 boolean，那么转换成 number；
>
> 如果一个操作值为 object 且另一方为 string、number 或者 symbol，就会把 object 转为原始类型再进行判断（调用 object 的 valueOf/toString 方法进行转换）。

## '+' 的隐式类型转换规则

> '+' 号操作符，不仅可以用作数字相加，还可以用作字符串拼接。仅当 '+' 号两边都是数字时，进行的是加法运算；如果两边都是字符串，则直接拼接，无须进行隐式类型转换。
>
> 除了上述比较常规的情况外，还有一些特殊的规则，如下所示。
>
> 如果其中有一个是字符串，另外一个是 undefined、null 或布尔型，则调用 toString() 方法进行字符串拼接；如果是纯对象、数组、正则等，则默认调用对象的转换方法会存在优先级，然后再进行拼接。
>
> 如果其中有一个是数字，另外一个是 undefined、null、布尔型或数字，则会将其转换成数字进行加法运算，对象的情况还是参考上一条规则。
>
> 如果其中一个是字符串、一个是数字，则按照字符串规则进行拼接。

## Object 的转换规则

> 对象转换的规则，会先调用内置的 [ToPrimitive] 函数，其规则逻辑如下：
>
> 如果部署了 Symbol.toPrimitive 方法，优先调用再返回；
>
> 调用 valueOf()，如果转换为基础类型，则返回；
>
> 调用 toString()，如果转换为基础类型，则返回；
>
> 如果都没有返回基础类型，会报错。
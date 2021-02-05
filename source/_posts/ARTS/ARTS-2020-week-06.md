---
title: ARTS-2020-week-06
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
date: 2021-02-01 09:35:56
---

# Algorithm

> 每周一个算法题：为了编程训练和学习

#### [剑指 Offer 03. 数组中重复的数字](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)

找出数组中重复的数字。


在一个长度为 n 的数组 nums 里的所有数字都在 0～n-1 的范围内。数组中某些数字是重复的，但不知道有几个数字重复了，也不知道每个数字重复了几次。请找出数组中任意一个重复的数字。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



```tsx
const findRepeatNumber = (nums) => {
  const uniqArr = [...new Set(nums)];
  let result = [];
  uniqArr.forEach(v => {
    const temp = nums.filter(i => i === v);
    if(temp.length > result.length) {
      result = temp;
    }
  })
  return result[0];
};
```




# Review

> 阅读并点评至少一篇英文技术文章：为了学习英文

[styling-web-components](https://css-tricks.com/styling-web-components/)

大致介绍了[emoji-picker-element](https://github.com/nolanlawson/emoji-picker-element) 的设计思想以及如何创建一个类似的组件来满足日常的使用。



# Tip

> 学习至少一个技术技巧：为了总结和归纳在日常工作中遇到的知识点

> [Array.prototype.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

以前一直没有怎么使用**reduce** ，最近发现使用 他来作为求和啊之类的很方便

```tsx
[1, 2, 3, 4, 5].reduce((a, b) => a + b);
// 10


let flattened = [[0, 1], [2, 3], [4, 5]].reduce(
  function(accumulator, currentValue) {
    return accumulator.concat(currentValue)
  },
  []
)
// flattened is [0, 1, 2, 3, 4, 5] // [[0, 1], [2, 3], [4, 5]].flat()



let names = ['Alice', 'Bob', 'Tiff', 'Bruce', 'Alice']

let countedNames = names.reduce(function (allNames, name) {
  if (name in allNames) {
    allNames[name]++
  }
  else {
    allNames[name] = 1
  }
  return allNames
}, {})
// countedNames is:
// { 'Alice': 2, 'Bob': 1, 'Tiff': 1, 'Bruce': 1 }



let people = [
  { name: 'Alice', age: 21 },
  { name: 'Max', age: 20 },
  { name: 'Jane', age: 20 }
];

function groupBy(objectArray, property) {
  return objectArray.reduce(function (acc, obj) {
    let key = obj[property]
    if (!acc[key]) {
      acc[key] = []
    }
    acc[key].push(obj)
    return acc
  }, {})
}

let groupedPeople = groupBy(people, 'age')
// groupedPeople is:
// {
//   20: [
//     { name: 'Max', age: 20 },
//     { name: 'Jane', age: 20 }
//   ],
//   21: [{ name: 'Alice', age: 21 }]
// }




// friends - an array of objects
// where object field "books" is a list of favorite books
let friends = [{
  name: 'Anna',
  books: ['Bible', 'Harry Potter'],
  age: 21
}, {
  name: 'Bob',
  books: ['War and peace', 'Romeo and Juliet'],
  age: 26
}, {
  name: 'Alice',
  books: ['The Lord of the Rings', 'The Shining'],
  age: 18
}]

// allbooks - list which will contain all friends' books +
// additional list contained in initialValue
let allbooks = friends.reduce(function(accumulator, currentValue) {
  return [...accumulator, ...currentValue.books]
}, ['Alphabet'])

// allbooks = [
//   'Bible', 'Harry Potter', 'War and peace',
//   'Romeo and Juliet', 'The Lord of the Rings',
//   'The Shining'
// ]



// Remove duplicate items in an array
let myArray = ['a', 'b', 'a', 'b', 'c', 'e', 'e', 'c', 'd', 'd', 'd', 'd']
let myOrderedArray = myArray.reduce(function (accumulator, currentValue) {
  if (accumulator.indexOf(currentValue) === -1) {
    accumulator.push(currentValue)
  }
  return accumulator
}, [])

console.log(myOrderedArray)
// ["a", "b", "c", "e", "d"]
// [...new Set(myOrderedArray)]




// Replace .filter().map() with .reduce()
const numbers = [-5, 6, 2, 0,];

const doubledPositiveNumbers = numbers.reduce((accumulator, currentValue) => {
  if (currentValue > 0) {
    const doubled = currentValue * 2;
    accumulator.push(doubled);
  }
  return accumulator;
}, []);

console.log(doubledPositiveNumbers); // [12, 4]




// Running Promises in Sequence
/**
 * Runs promises from array of functions that can return promises
 * in chained manner
 *
 * @param {array} arr - promise arr
 * @return {Object} promise object
 */
function runPromiseInSequence(arr, input) {
  return arr.reduce(
    (promiseChain, currentFunction) => promiseChain.then(currentFunction),
    Promise.resolve(input)
  )
}

// promise function 1
function p1(a) {
  return new Promise((resolve, reject) => {
    resolve(a * 5)
  })
}

// promise function 2
function p2(a) {
  return new Promise((resolve, reject) => {
    resolve(a * 2)
  })
}

// function 3  - will be wrapped in a resolved promise by .then()
function f3(a) {
 return a * 3
}

// promise function 4
function p4(a) {
  return new Promise((resolve, reject) => {
    resolve(a * 4)
  })
}

const promiseArr = [p1, p2, f3, p4]
runPromiseInSequence(promiseArr, 10)
  .then(console.log)   // 1200




// Function composition enabling piping
// Building-blocks to use for composition
const double = x => x + x
const triple = x => 3 * x
const quadruple = x => 4 * x

// Function composition enabling pipe functionality
const pipe = (...functions) => input => functions.reduce(
    (acc, fn) => fn(acc),
    input
)

// Composed functions for multiplication of specific values
const multiply6 = pipe(double, triple)
const multiply9 = pipe(triple, triple)
const multiply16 = pipe(quadruple, quadruple)
const multiply24 = pipe(double, triple, quadruple)

// Usage
multiply6(6)   // 36
multiply9(9)   // 81
multiply16(16) // 256
multiply24(10) // 240


// Write map using reduce
if (!Array.prototype.mapUsingReduce) {
  Array.prototype.mapUsingReduce = function(callback, thisArg) {
    return this.reduce(function(mappedArray, currentValue, index, array) {
      mappedArray[index] = callback.call(thisArg, currentValue, index, array)
      return mappedArray
    }, [])
  }
}

[1, 2, , 3].mapUsingReduce(
  (currentValue, index, array) => currentValue + index + array.length
) // [5, 7, , 10]
```



# Share

> 分享一篇有观点和思考的技术文章：为了建立影响力，能够输入价值观

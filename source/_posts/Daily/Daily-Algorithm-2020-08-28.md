---
title: Daily-Algorithm-2020-08-28
date: 2020-08-28 09:11:00
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [Fizz Buzz](https://leetcode-cn.com/problems/fizz-buzz/)

## Desc

写一个程序，输出从 1 到 n 数字的字符串表示。

1. 如果 n 是3的倍数，输出“Fizz”；

2. 如果 n 是5的倍数，输出“Buzz”；

3.如果 n 同时是3和5的倍数，输出 “FizzBuzz”。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/fizz-buzz
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var fizzBuzz = function(n) {
  const result = [];
  for(let i = 1; i <= n; i++) {
    if(three(i) && five(i)) {
      result.push('FizzBuzz');
    } else if(three(i) && !five(i)) {
      result.push('Fizz');
    } else if(!three(i) && five(i)) {
      result.push('Buzz');
    } else {
      result.push(`${i}`);
    }
  }
  return result;
};

const three = v => v % 3 === 0;
const five = v => v % 5 === 0;
```


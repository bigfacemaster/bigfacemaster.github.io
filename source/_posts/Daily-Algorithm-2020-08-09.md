---
title: Daily-Algorithm-2020-08-09
date: 2020-08-09 09:38:47
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [猜数字大小](https://leetcode-cn.com/problems/guess-number-higher-or-lower/)

## Desc

猜数字游戏的规则如下：

每轮游戏，系统都会从 1 到 n 随机选择一个数字。 请你猜选出的是哪个数字。
如果你猜错了，系统会告诉你这个数字比系统选出的数字是大了还是小了。
你可以通过调用一个预先定义好的接口 guess(int num) 来获取猜测结果，返回值一共有 3 种可能的情况（-1，1 或 0）：

-1 : 系统选出的数字比你猜测的数字小
 1 : 系统选出的数字比你猜测的数字大
 0 : 恭喜！你猜对了！

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/guess-number-higher-or-lower
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。



## Code

```js
var guessNumber = function(n) {
    let left = 1;
    let right = n;
    let mid;
    while(left <= right){
        mid = parseInt((left + right)/2);
        const val = guess(mid);
        if(val === 0){
            break
        }else if(val === 1){
            left = mid + 1;
        }else if(val === -1){
            right = mid-1;
        }
    }

    return mid;
};
```


---
title: Daily-Algorithm-2020-07-10
date: 2020-07-10 09:41:57
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [去掉最低工资和最高工资后的工资平均值](https://leetcode-cn.com/problems/average-salary-excluding-the-minimum-and-maximum-salary/)

## Desc

给你一个整数数组 salary ，数组里每个数都是 唯一 的，其中 salary[i] 是第 i 个员工的工资。

请你返回去掉最低工资和最高工资以后，剩下员工工资的平均值。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/average-salary-excluding-the-minimum-and-maximum-salary
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

## Code

```js

var average = function(salary) {
  const sorted = salary.sort((a, b) => a - b );
  console.log(sorted);
  sorted.pop();
  sorted.shift();
  let sum = 0;
  sorted.forEach( v => sum += v);
  return sum / sorted.length; 
};
```


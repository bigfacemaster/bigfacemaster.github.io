---
title: Daily-Algorithm-2020-09-23
date: 2020-09-23 09:16:32
tags: [Algorithm, 算法]
category: [Algorithm, 算法]
---

# [二叉搜索树的最小绝对差](https://leetcode-cn.com/problems/minimum-absolute-difference-in-bst/)

## Desc

给你一棵所有节点为非负值的二叉搜索树，请你计算树中任意两节点的差的绝对值的最小值。



## Code

```js
var getMinimumDifference = function(root) {
  const arr = [];

  const inorder = (node) => {
    if (node){
        inorder(node.left);
        arr.push(node.val);
        inorder(node.right);
    }
  }
  
  inorder(root);

  let minDiffValue = Number.MAX_SAFE_INTEGER;

  for (let i = 0; i < arr.length - 1; i++){
      minDiffValue = Math.min(minDiffValue, arr[i + 1] - arr[i]);
  }

  return minDiffValue;

};
```


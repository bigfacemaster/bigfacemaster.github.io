---
title: 检测一个数组是否为另一个数组的子集Detects whether an array is a subset of another array
date: 2017-05-10 22:39:56
tags: [array, subset]
category: code
---
# 检测一个数组是否为另一个数组的子集Detects whether an array is a subset of another array
```javascript
// arr1.length > arr2.length
function dectectArray( arr1, arr2) {
    let i = 0;
    let j = 0;
    if( arr1.length < arr2.length) {
        return false;
    }
    while( i < arr2.length && j < arr1.length){
        if( arr1[j] < arr2[i]){
            j++;
        } else if( arr1[j] === arr2[i] ){
            j++;
            i++;
        } else if( arr1[j] > arr2[i]){
            return false;
        }
    }
    if( i < arr2.length ){
        return false;
    } else {
        return true;
    }
}
```

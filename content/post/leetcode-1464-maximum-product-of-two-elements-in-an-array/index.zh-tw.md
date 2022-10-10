---
title: 1464. 一個陣列中兩個元素的最大乘積
description: 1464. Maximum Product of Two Elements in an Array
date: 2022-10-05
slug: maximum-product-of-two-elements-in-an-array
# image: helena-hertz-wWZzXlDpMog-unsplash.jpg
categories:
    - Leetcode
    - Easy
---

## 題目

### 原題目
```diff
+ 英文:
- Given the array of integers nums, you will choose two different indices i and j of that array. Return the maximum value of (nums[i]-1)*(nums[j]-1).

+ 中文:
- 給定一個整數陣列 nums，請你選擇陣列中兩個不同的指數。回傳 (nums[i]-1)*(nums[j]-1) 的最大值。
- 請回傳 nums 的 累積和。
```

### 測資一

```diff
+ 輸入: nums = [3,4,5,2]
+ 輸出: 12
- 解釋: 如果指數 i = 1 和 j = 3(索引值從0開始)，可以得到最大值，(nums[1]-1)*(nums[2]-1) = (4-1)*(5-1) = 3*4 = 12 。 
```

### 測資二

```diff
+ 輸入: nums = [1,5,4,5]
+ 輸出: 16
- 解釋: 如果指數 i = 1 和 j = 3(索引值從0開始)，可以得到最大值，(5-1)*(5-1) = 16 。
```

### 測資三

```diff
+ 輸入: nums = [3,7]
+ 輸出: 12
```

## 解題思路
再這題當中，分成兩個部分：
- 要找到最大值的索引 i 和第二大值的索引 j。
- 代入公式 (nums[1]-1)*(nums[2]-1)，並回傳結果。

### Java 思路
先排序陣列，即可取得最大值和最小值。套上公式即可。

### Python 思路
跟Java解題思路是一樣的。

## 答案
此題答案以 Java 解！
```java
class Solution {
    public int maxProduct(int[] nums) {
        
        // 先排序陣列
        Arrays.sort(nums);
        
        // 代入公式並回傳
        return (nums[nums.length-1] - 1) * (nums[nums.length-2] - 1);
    }
}
```
<!-- > 思念是最暖的憂傷像一雙翅膀  
> 讓我停不了飛不遠在過往遊蕩  
> 不告而別的你 就算為了我著想  
> 這麼沉痛的呵護 我怎麼能翱翔
> 
> *[最暖的憂傷 - 田馥甄](https://www.youtube.com/watch?v=3aypp_YlBzI)* -->
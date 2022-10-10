---
title: 747. 至少是其他數字兩倍的最大數
description: 747. Largest Number At Least Twice of Others
date: 2022-10-04
slug: largest-number-at-least-twice-of-others
# image: helena-hertz-wWZzXlDpMog-unsplash.jpg
categories:
    - Leetcode
    - Easy
---

## 題目

### 原題目
```diff
+ 英文:
- You are given an integer array nums where the largest integer is unique.
- Determine whether the largest element in the array is at least twice as much as every other number in the array. If it is, return the index of the largest element, or return -1 otherwise.

+ 中文:
- 給定一個整數陣列 nums，其中有一個最大整數是唯一的
- 檢查陣列之最大元素是否至少是陣列中其他每個數字的兩倍。如果是，則回傳最大元素之索引，否則回傳 -1。
```

### 測資一

```diff
+ 輸入: nums = [3,6,1,0]
+ 輸出: 1
- 解釋: 6 是最大的整數。對於其他陣列來說，6至少是其他元素的兩倍。6的索引值是1，所以回傳1。
```

### 測資二

```diff
+ 輸入: nums = [1,2,3,4]
+ 輸出: -1
- 解釋: 4 小於三的兩倍，所以回傳 -1。
```

## 解題思路
在這題當中，nums 為陣列，需要先找出最大的值，遍歷搜尋比他兩倍大的數字，如果有比他大的數字，就回傳-1，否則回傳索引值。以測資一來說，6為最大的數字，遍歷搜尋比6大的數字，3*2小於等於6，因此回傳索引值1。

再以測資二為例，4為最大數，搜尋其他數字的兩倍比4大的數字，3*2>4，明顯比他大，所以回傳-1。

### Java 思路
先定義最大數字，然後遍歷搜尋，可以用演算法，也可以用一般方式來解。

### Python 思路
跟Java解題思路是一樣的。

## 答案
此題答案以 Python 解！
```Python
class Solution(object):
    def dominantIndex(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        
        # 先宣告計數器為0
        counter = 0
        
        # 將 nums 的值以 i 的形式遍歷跑
        for i in nums:
            # 如果 每個值乘二 大於 最大值
            if i*2 > max(nums):

                # 計數器+1
                counter += 1
                
        # 如果沒有搜尋到
        if counter == 0:
            # 回傳 -1
            return -1
        else:
            # 否則回傳最大值的索引值
            return nums.index(max(nums))
```
<!-- > 思念是最暖的憂傷像一雙翅膀  
> 讓我停不了飛不遠在過往遊蕩  
> 不告而別的你 就算為了我著想  
> 這麼沉痛的呵護 我怎麼能翱翔
> 
> *[最暖的憂傷 - 田馥甄](https://www.youtube.com/watch?v=3aypp_YlBzI)* -->
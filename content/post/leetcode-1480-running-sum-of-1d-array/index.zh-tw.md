---
title: 1480. 一維陣列累積和
description: 1480. Running Sum of 1d Array
date: 2022-10-05
slug: running-sum-of-1d-array
# image: helena-hertz-wWZzXlDpMog-unsplash.jpg
categories:
    - Leetcode
    - Easy
---

## 題目

### 原題目
```diff
+ 英文:
- Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).
- Return the running sum of nums.

+ 中文:
- 給定一個陣列，陣列「累積和」的計算公式為「runningSum[i] = sum(nums[0]…nums[i]) 」。
- 請回傳 nums 的 累積和。
```

### 測資一

```diff
+ 輸入: nums = [1,2,3,4]
+ 輸出: [1,3,6,10]
- 解釋: 累積和計算過程為 [1, 1+2, 1+2+3, 1+2+3+4] 。
```

### 測資二

```diff
+ 輸入: nums = [1,1,1,1,1]
+ 輸出: [1,2,3,4,5]
- 解釋: 累積和計算過程為 [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1] 。
```

## 解題思路
再這題當中，i項為i-1項+原i項之和，可以用迴圈去跑，要注意的是 i 為 0 時不需要加，也就是第一項不用加前項，否則會出現索引值找不到的錯誤。

### Java 思路
使用 nums.length取得陣列長度，然後開始慢慢加即可。

### Python 思路
跟Java解題思路是一樣的。

## 答案
此題答案以 Python 解！
```Python
class Solution(object):
    def runningSum(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        
        # 先宣告一個空串列
        lst = []
        
        # i 從 0 跑至 nums的長度
        for i in range(len(nums)):
            # 第一項
            if i == 0:
                lst.append(nums[i])
            #第二項開始
            else:
                lst.append(nums[i] + lst[i-1])
                
        return lst
```
<!-- > 思念是最暖的憂傷像一雙翅膀  
> 讓我停不了飛不遠在過往遊蕩  
> 不告而別的你 就算為了我著想  
> 這麼沉痛的呵護 我怎麼能翱翔
> 
> *[最暖的憂傷 - 田馥甄](https://www.youtube.com/watch?v=3aypp_YlBzI)* -->
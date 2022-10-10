---
title: 4. 尋找兩個已排序陣列的中間值
description: 4. Median of Two Sorted Arrays
date: 2022-10-04
slug: median-of-two-sorted-arrays
# image: helena-hertz-wWZzXlDpMog-unsplash.jpg
categories:
    - Leetcode
    - Hard
---

## 題目

### 原題目
```diff
+ 英文:
- Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.
- The overall run time complexity should be O(log (m+n)).

+ 中文:
- 給定兩個已排序過的陣列 num1 和 num2，大小分別為 m 和 n，回傳兩個已排序陣列的中間值。
- 總執行時間複雜度為 O(log (m+n))。
```

### 測資一

```diff
+ 輸入: nums1 = [1,3], nums2 = [2]
+ 輸出: 2.00000
- 解釋: 合併後陣列 = [1,2,3] 中間值為 2.
```

### 測資二

```diff
+ 輸入: nums1 = [1,2], nums2 = [3,4]
+ 輸出: 2.50000
- 解釋: 合併後陣列 = [1,2,3,4] 中間值為 (2 + 3) / 2 = 2.5.
```

## 解題思路
在這題當中，num1 及 num2 皆為陣列，需要把這兩個東西合再一起，以測資一來說，nums1 + nums2 就會是 [1, 3, 2]，接下來因為要取中間值所以需要排序，排序過後會是[1, 2, 3]，中間值即為2。

再以測資二為例，nums1 + nums2 就會是 [1, 2, 3, 4]，排序過後仍然一樣，中間值則為(2+3)/2=2.5，答案即為2.5

### Java 思路
因為函數傳進了兩個陣列，因此在宣告一個整數陣列，將兩個陣列放置在一起，接下來再使用sort()方法將陣列排序即可開始寫if-else取值。

### Python 思路
跟Java解題思路是一樣的，先宣告一個陣列 lst，將num1 及 num2 放入 lst，再開始if-else解即可。

## 答案
此題答案以 Python 解！
```Python
class Solution(object):
    def findMedianSortedArrays(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        # 先宣告一個lst 將 num1 放入
        lst = nums1

        # 將 num2 每筆資料都放入 i 遍歷跑
        for i in nums2:
            # 將 nums2 放入 lst，即達成 lst = num1 + num2
            lst.append(i)

        # 將 lst 進行排序
        lst = sorted(lst)

        # 宣告答案值為0
        ans = 0
        
        # 如果 lst的數量為偶數
        if len(lst) % 2 == 0:
            # 則取 中間兩位之平均值，回寫入ans
            ans = float(lst[len(lst)/2-1] + lst[len(lst)/2])/2
        else:
            # 否則取中間值
            ans = lst[len(lst)//2]

        # 回傳答案
        return ans
```
<!-- > 思念是最暖的憂傷像一雙翅膀  
> 讓我停不了飛不遠在過往遊蕩  
> 不告而別的你 就算為了我著想  
> 這麼沉痛的呵護 我怎麼能翱翔
> 
> *[最暖的憂傷 - 田馥甄](https://www.youtube.com/watch?v=3aypp_YlBzI)* -->
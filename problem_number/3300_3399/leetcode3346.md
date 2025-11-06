# 3346. Maximum Frequency of an Element After Performing Operations I 

https://leetcode.com/problems/maximum-frequency-of-an-element-after-performing-operations-i

## 提示
list 中的數字會影響一個範圍的幾個數字，只處理邊界時間效率好。

## 解法
作進階題 [3347.](./leetcode3347.md) 找到更好的解法。sliding window 作兩次，一次計數轉換為`nums`中有的數字，另一次計數轉換為`nums`中沒有的數字 [lee's solution]。  
prefix sum 配合差分表處理。  
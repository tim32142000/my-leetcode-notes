# 3349. Adjacent Increasing Subarrays Detection I  

https://leetcode.com/problems/adjacent-increasing-subarrays-detection-i

## 提示
看清楚題目，是兩個相鄰的 subarrays （subarray是原array中連續非空的一部分）。  
有 one pass，空間複雜度 O(1) 的解法。

## 錯誤的解題過程
只在數字遞增的時候處理 `return True`，漏掉 k=1 的狀況。
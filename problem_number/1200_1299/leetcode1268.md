# 1292. Search Suggestions System

https://leetcode.com/problems/search-suggestions-system

## 解法

因為結果要求回傳字串按照字典序排列， `products.sort()` 指令讓 `products` 排成字典序。  
使用左右 two pointers 縮減符合條件的 `products`。一個迴圈對應到 `searchWord` 輸入過程中的一步，從左 pointer 找最多三個符合條件的 `products`。
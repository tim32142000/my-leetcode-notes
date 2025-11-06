# 3347. Maximum Frequency of an Element After Performing Operations II  

https://leetcode.com/problems/maximum-frequency-of-an-element-after-performing-operations-ii

[3346.](leetcode3346.md) 的進階題
## 提示
sliding window 作兩次，一次計數轉換為`nums`中有的數字，另一次計數轉換為`nums`中沒有的數字[lee's solution]。

## 解題過程
prefix sum 配合差分表，想到的幾個方法超過時間或記憶體限制。
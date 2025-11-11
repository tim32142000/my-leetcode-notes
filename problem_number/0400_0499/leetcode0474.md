# 474. Ones and Zeroes

https://leetcode.com/problems/ones-and-zeroes

## 提示  
Dynamic Programming。

## 解法
`dp[i][j] = max(dp[i][j],dp[i-zeros][j-ones]+1)`，`i, j`從大到小更新 `dp`，確保使用上一個字串的小`i, j`數值更新`dp[i][j]`，避免重複使用字串。
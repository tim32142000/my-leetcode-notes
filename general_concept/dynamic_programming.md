# Dynamic Programming

## 1. DP 的四要素

> 1. 狀態定義 (State Definition)：用白話文解釋 dp[i][j] 代表什麼  
> 2. 狀態轉移方程 (Transition Equation)：大問題如何由小問題推導出來 
> 3. 邊界條件與初始化 (Base Case & Initialization)：最小的問題答案是什麼 
> 4. 計算順序 (Ordering)：是從左到右、從上到下，還是區間由小到大 

## 2. DP 的大局觀：常見的模型分類

* 線性 DP：最基礎，如爬樓梯、打家劫舍 (House Robber)。  
* 背包問題 (Knapsack)：0/1 背包、完全背包。核心在於「選或不選」與「剩餘重量」。  
* 區間 DP：狀態通常是 dp[i][j] 表示區間 [i,j] 的最優解，如矩陣鏈乘法、石子合併。  
* 序列比對 (Sequence Alignment)：這題 (1458) 與 Longest Common Subsequence (最長公共子序列)、Edit Distance 都屬於這類。通常使用二維矩陣。  
* 狀態壓縮 DP (Bitmask DP)：當狀態與集合有關，且 N 很小時（例如 N≤20）。  

### 最長公共子序列類型題目
在二維的 dp 陣列中，更新 dp[i+1][j+1] 只依賴 dp[i][j]、dp[i][j+1]、dp[i+1][j]。可以狀態壓縮到一維 dp 陣列以及儲存之前的左上角元素。  

```python
for i in range(len1):
    prev_upleft = 0 # 注意，曾經忘記過這行
    for j in range(len2):
        update_temp = max(prev_upleft + s1[i] == s2[j], dp[j], dp[j+1])
        prev_upleft, dp[j+1] = dp[j+1], update_temp
```

## 相關題目
[1458. Max Dot Product of Two Subsequences
](https://leetcode.com/problems/max-dot-product-of-two-subsequences) Hard
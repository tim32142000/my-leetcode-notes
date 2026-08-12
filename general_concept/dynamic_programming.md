# Dynamic Programming

### 1. DP 的四要素

> 1. 狀態定義 (State Definition)：用白話文解釋 dp[i][j] 代表什麼  
> 2. 狀態轉移方程 (Transition Equation)：大問題如何由小問題推導出來 
> 3. 邊界條件與初始化 (Base Case & Initialization)：最小的問題答案是什麼 
> 4. 計算順序 (Ordering)：是從左到右、從上到下，還是區間由小到大 

### 2. DP 的大局觀：常見的模型分類

* 線性 DP：最基礎，如爬樓梯、打家劫舍 (House Robber)。  
* 背包問題 (Knapsack)：0/1 背包、完全背包。核心在於「選或不選」與「剩餘重量」。  
* 區間 DP：狀態通常是 dp[i][j] 表示區間 [i,j] 的最優解，如矩陣鏈乘法、石子合併。  
* 序列比對 (Sequence Alignment)：這題 (1458) 與 Longest Common Subsequence (最長公共子序列)、Edit Distance 都屬於這類。通常使用二維矩陣。  
* 狀態壓縮 DP (Bitmask DP)：當狀態與集合有關，且 N 很小時（例如 N≤20）。  

---

## 題目

### 編輯距離題目

#### 72. Edit Distance

目標是用最小的編輯次數讓 word1 變成 word2 。  編輯方法有插入、刪除、替換子母。  

用 index i 比對 word1 的第 i 個字母，  index j  比對 word2 的第 j 個字母，從字尾開始比對到字頭，理清楚各種編輯方法的關係。

如果 word1[i] == word2[j] ，那 dp[i][j] = dp[i-1][j-1]。

word1[i] != word2[j] 的話，那要選用一種編輯方法。

如果使用插入字母，插入的位置在 i 右側，比對 word1 的 index i 不動。 插入的字母是 word2[j]，讓相同的字母多一個，比對 word2 的 index 減一。 dp[i][j] = dp[i][j-1]。

如果使用刪除字母，那麼 word1[i] 被刪除，比對 word1 的 index 減一，比對 word2 的 index 不變。 dp[i][j] = dp[i-1][j]

如果使用替換字母，那麼 word1[i] 變成 word2[j]，比對 word1 和 word2 的 index 都減一。 dp[i][j] = dp[i-1][j-1]

---

### 最長公共子序列類型題目
在二維的 dp 陣列中，更新 dp[i+1][j+1] 只依賴 dp[i][j]、dp[i][j+1]、dp[i+1][j]。可以狀態壓縮到一維 dp 陣列以及儲存之前的左上角元素。  

```python
for i in range(len1):
    prev_upleft = 0 # 注意，曾經忘記過這行
    for j in range(len2):
        update_temp = max(prev_upleft + s1[i] == s2[j], dp[j], dp[j+1])
        prev_upleft, dp[j+1] = dp[j+1], update_temp
```

---


### 買股票題目

#### 714. Best Time to Buy and Sell Stock with Transaction Fee  

在同一天只有持股和不持股兩種狀態。  
使用 dp 的概念，考慮第 i 天的狀態。  
第 i 天的可能狀態是持股和不持股。  
再回推第 i 天的狀態是怎麼從第 i-1 天的狀態轉移過去的。

---


### 拿走石頭題目

#### 877. Stone Game

題目給了 piles，表示第 i 堆的石頭數。玩家可以選擇拿開始或結尾的整堆石頭。  

這題有數學解法，這篇文章主要記錄 dp 解法。  

解題關鍵是定義好 dp[i][j] ，以及狀態轉移的關係。

定義 dp[i][j] 為，石頭範圍從索引 i 到 j 時，行動回合的玩家A 能夠比另一位玩家B 多拿多少石頭。  

計算狀態轉移，若玩家A 拿走了第 i 堆石頭， 玩家B 得dp[i+1][j] 分。若玩家A 拿走了第 j 堆石頭，玩家B 得dp[i][j-1]分。  
`dp[i][j] = max(piles[i] - dp[i + 1][j], piles[j] - dp[i][j - 1])`

填dp array 的時候注意，更新 i到j 長度是 `length` 的資料時，需要使用長度 `length-1` 的dp array 資料，因此需要斜著填 dp array。

```python
# 依序計算不同長度的區間 (長度從 2 到 n)
for length in range(2, n + 1):
    for i in range(n - length + 1):
        j = i + length - 1
        # 狀態轉移
        dp[i][j] = max(piles[i] - dp[i + 1][j], piles[j] - dp[i][j - 1])
```


---

#### 1406. Stone Game III


---
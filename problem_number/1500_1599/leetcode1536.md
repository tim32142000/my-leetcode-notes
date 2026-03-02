# 1536. Minimum Swaps to Arrange a Binary Grid

https://leetcode.com/problems/minimum-swaps-to-arrange-a-binary-grid

## Topics
Array, Greedy, Matrix

## 解法
1. **轉換問題：** 對於第 i 列（從 0 開始），為了滿足題目條件（主對角線以上全是 0），該列右側必須至少有 n−1−i 個連續的 0。

2. **貪心策略：** 從第一列開始，依序尋找下方最靠近且符合條件的列，將其交換上來。

3. **無解判定：** 如果在下方找不到任何一列符合當前位置所需的 0 的數量，則回傳 -1。
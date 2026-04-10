# 1545. Find Kth Bit in Nth Binary String

https://leetcode.com/problems/find-kth-bit-in-nth-binary-string

## Topics
Senior, String, Recursion, Simulation

## 解法
不需要實際構建出完整的字串 $S_n$​（因為 n=20 時字串長度會達到約 100 萬），而是利用其對稱性和遞迴結構來尋找第 k 個字元。

1. **長度規律：** $S_n$​ 的長度為 $2^n−1$。

2. **結構劃分：** $S_n$​ 可以分為三部分：

    - 前半部分 (1 到 mid−1)：等於 $S_{n−1}$​。

    - 中間部分 (mid)：永遠是 "1"。

    - 後半部分 (mid+1 到 2n−1)：是 $S_{n−1}$​ **反轉（reverse）且反轉位元（invert）** 後的結果。

3. **遞迴邏輯：**

    -  如果 k 在前半部：直接在 $S_{n−1}$​ 中找第 k 位。

    - 如果 k 正好是中間位：回傳 "1"。

    - 如果 k 在後半部：尋找 $S_{n−1}$​ 對應位置的字元，並將其反轉（0 變 1，1 變 0）。對應位置的計算公式為：new_k=Total Length−k+1。
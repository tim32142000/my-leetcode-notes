# Complexity and Scale

| 時間複雜度 | 最大規模 (N) | 適用場景 / 演算法 |
| :--- | :--- | :--- |
| $O(2^N)$ | $N \le 20 \sim 25$ | 遞迴窮舉、位元遮罩 DP (Bitmask DP)。 |
| $O(N^4)$ | $N \le 100 \sim 500$ | 建議暴力模擬，把時間留給別題。 |
| $O(N^3)$ | $N \le 200 \sim 500$ | 矩陣乘法、Floyd-Warshall 最短路徑。 |
| $O(N^2)$ | $N \le 5,000$ | 雙重迴圈、簡單 DP、區間計算。 |
| $O(N \log N)$ | $N \le 10^6$ | 排序 (Sorting)、Segment Tree、Heap。 |
| $O(N)$ | $N \le 10^7 \sim 10^8$ | 線性掃描、單調棧 (Monotonic Stack)、雙指標。 |
| $O(\sqrt{N})$ | $N \le 10^{14}$ | 質數判斷、整除分塊。 |
| $O(\log N)$ | $N$ 幾乎無限大 | 二分搜尋 (Binary Search)、快速冪。 |
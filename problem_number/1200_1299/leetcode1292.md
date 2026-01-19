# 1292. Maximum Side Length of a Square with Sum Less than or Equal to Threshold

https://leetcode.com/problems/maximum-side-length-of-a-square-with-sum-less-than-or-equal-to-threshold

## 解法
時間複雜度：O(m x n)，需要聰明的檢查方式。  
空間複雜度：O(m x n)。  
預存一個 2-D 的 prefix sum 矩陣，數值是左或上方的所有元素和。再用排容原理快速計算選定範圍的正方形數值和。  
聰明的檢查方式：
```python
ans = 0
# 貪心滑窗遍歷
for i in range(m):
    for j in range(n):
        # 嘗試是否有更大的邊長 ans + 1 (以 i, j 為右下角)
        # 確保邊界不越界
        if i - ans >= 0 and j - ans >= 0:
            # 計算以 (i, j) 為右下角，邊長為 ans + 1 的正方形和
            # 左上角座標為 (i - ans, j - ans)
            max_side = (
                up_left_sum[i + 1][j + 1]
                - up_left_sum[i - max_side][j + 1]
                - up_left_sum[i + 1][j - max_side]
                + up_left_sum[i - max_side][j - max_side]
            )
            
            if max_side <= threshold:
                ans += 1
```
一個邊長 `length` 檢查到一個條件成立後就檢查 `length + 1`，不會多檢查。而檢查成立的元素，它的左上角一定會讓 `length - 1`的檢查通過。依此類推，通過的長度會從 0 逐步加一成為 `length`。
# 3047. Find the Largest Area of Square Inside Two Rectangles

https://leetcode.com/problems/find-the-largest-area-of-square-inside-two-rectangles

## 解法  
參考解答，解法是用雙迴圈兩兩比較長方形重疊的最大正方形。  

## 其他想法  
因為只需要兩個長方形重疊。存起前面已經被長方形蓋住的地方（聯集），one-pass 逐一檢查長方形和前面長方形交集出的最大正方形。對比解答發現不規則形和長方形的交集最大正方形比較難計算，還沒想到方法。  
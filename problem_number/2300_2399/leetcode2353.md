# 2353. Design a Food Rating System  

https://leetcode.com/problems/design-a-food-rating-system

## 整理
heap 化的時間複雜度是 O(n)。要被呼叫 $2*10^4$ 次，時間複雜度 O(n) 的表現不夠好。對已經排好序的 heap，去修改 heap 中的資料後再 heap 化的代價太大，這題有其他方法。

## 提示

Gemini:  
不修改 heap 中元素的資料，而是用另一個變數存下 food 最新評分，比對可知 `heap[0]` 是有效的最新評分或舊評分。  
"Lazy Deletion" 的策略：  
1. 更新時（changeRating）：不在乎舊資料，直接加入新資料。這一步超快，因為只是一個簡單的 push 操作。  
2. 查詢時（highestRated）：在找最高評分時，才順便處理這些舊資料。while 迴圈會自動把堆頂那些過時的項目彈出，直到找到一個與 self.food_data 吻合的有效項目。雖然 while 迴圈可能執行多次，但在攤銷（amortized）的意義上，每次 highestRated 的平均時間複雜度仍然很低，因為每次彈出的舊資料，都是之前某次 changeRating 加入的，可以視為分攤了那次更新的清理成本。
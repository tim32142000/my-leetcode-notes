# 757. Set Intersection Size At Least Two

https://leetcode.com/problems/set-intersection-size-at-least-two

## 提示

### Topics
Array, Greedy, Sorting

## 解法  
因為每個區間至少要出兩個數字，對於排序好的區間，存下前面 containing set 最大的兩個數字，處理新區間時，檢查這兩個數字有沒有在區間範圍內再作對應的處理就可以。  
這題可以用 Greedy，排序先處理早結束的、晚開始的。  

## 解題過程  

有考慮過存 containing set 的所有元素，最後 `return len(containing_set)`。但因為檢查區間範圍內所有數字是否在前面區間收集到的 containing set 沒效率，覺得不可行而沒有實行。追蹤關鍵兩個數字，檢查有沒有在區間範圍內比較有效率。

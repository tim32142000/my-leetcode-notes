# 3634. Minimum Removals to Balance Array 

https://leetcode.com/problems/minimum-removals-to-balance-array

Gemini：正確的策略應該是：固定一個最小值，並找出在此最小值限制下，能包含最多元素的右邊界。
Gemini的程式碼是跑 `right` 的 for 迴圈，內部 while 迴圈收縮 `left`，這樣子 while 迴圈不用檢查 `left` 出界。
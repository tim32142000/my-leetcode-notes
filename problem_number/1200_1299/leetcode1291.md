# 1291. Sequential Digits

https://leetcode.com/problems/sequential-digits

題目要回傳 `[low, high]` 範圍內是 Sequential Digits 的整數。 Sequential Digits 指的是整數從左邊第二位開始，每個位數比左邊那一位數只多 1 。  

輸出的整數 list 要從小到大排序。  

迴圈按照整數位數少到多作，內部再用一個起始位數的迴圈，依順序把範圍內的整數放入 `result` list。


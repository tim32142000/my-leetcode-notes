# 3542. Minimum Operations to Convert All Elements to Zero   

https://leetcode.com/problems/minimum-operations-to-convert-all-elements-to-zero

## 提示
Topic tag: monotonic stack。

## 解題過程
用 set 存之前出現過的數字，只保留小於等於當前數字的數字，想到的作法會超時。有序的 monotonic stack 減少比較次數，增加執行速度。  
# 1930. Unique Length-3 Palindromic Subsequences  

https://leetcode.com/problems/unique-length-3-palindromic-subsequences

## 提示  
英文字母總共 26 個，比大部分字串長度短（3 <= s.length <= 10^5），針對字母解題。  
長度為 3 的回文子序列用幾個變數就能追蹤處理。  

## 解法  
找到每個字母的最前和最後 index，中間的出現字母種類是其中一個字母的結果。對 26 個英文字母加總得到這題的答案。
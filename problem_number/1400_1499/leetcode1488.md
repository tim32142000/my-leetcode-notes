# 1488. Avoid Flood in The City

https://leetcode.com/problems/avoid-flood-in-the-city

## 提示  


## 解題過程  
使用 python 的 OrderedDict 通過，時間比 96% 人快但是記憶體只比 27%人少。  
後來嘗試用 `a = SortedList()`和 binary search。錯用成 `bisect_left(a,target)` 執行時間久，`a.bisect_left(target)`快很多。  
程式碼只有一行之差，執行時間差很多  
`i_use = bisect_right(i_dry,lake_full_i[rain])`  
Runtime 430ms Beats 5.12%  

`i_use = i_dry.bisect_right(lake_full_i[rain])`  
Runtime 155ms Beats 87.44%  

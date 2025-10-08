# 2300. Successful Pairs of Spells and Potions  

https://leetcode.com/problems/successful-pairs-of-spells-and-potions

## 提示  
### Topics  
Array, Two Pointers, Binary Search, Sorting  

排序後的 index 對應到個數。  

整數除法向上取整 (ceiling)：  
`min_potion = (success+spell−1)//spell` [gemini]  
（加上 (spell-1) 讓餘數 1~(spell-1) 的除法結果加一，整除不用加）  


## 解題過程
用了 Counter()，超時。Counter 只在有重複元素的時候可以省時間，對這題的幫助不大。  
初始化 `ans = [0]*len_s` ，比`ans = [0 for _ in range(len_s)]` 和空 list 再 append 更省記憶體。可能是因為這題記憶體複雜度 O(1)，讓其他地方的記憶體差距變明顯。  

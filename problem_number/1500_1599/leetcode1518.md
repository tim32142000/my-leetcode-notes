# 1518. Water Bottles

https://leetcode.com/problems/water-bottles


## 提示  
模擬法直觀，有不容易想到的數學解法。  

## 解釋  
`numExchange`個空瓶換一瓶飲料和一個空瓶。  
每次交換，空瓶剩餘量減少`numExchange`-1，交換回的總瓶數是 (可交換的空瓶)//(`numExchange`-1)。  
考慮空瓶數剛好被 (`numExchange`-1) 整除的時候，最後一次剩 (`numExchange`-1) 其實不能交換。  
要交換 n 瓶，至少需要 n*(`numExchange`-1)+1 個空瓶。  
移項得到交換瓶數 n = (`numBottles`-1)//(`numExchange`-1)。
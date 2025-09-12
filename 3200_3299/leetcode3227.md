# 3227. Vowels Game in a String

https://leetcode.com/problems/vowels-game-in-a-string

## 解題過程  
Alice 的回合輸的局面：  
1. `s == ""`  
2. `s`沒有母音  
3. 留下偶數個母音給對方

Bob 的回合輸的局面：  
1. `s == ""`  
2. `s`只有一個母音，沒有子音
3. 留下奇數個母音給對方  

如果`s`有偶數個母音，Alice 拿奇數個母音，剩奇數個母音。如果`s`有奇數個母音，Alice 全拿完獲勝。
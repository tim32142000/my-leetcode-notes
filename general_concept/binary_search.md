因為看了 labuladong 的書，開始使用左閉右開區間寫 binary search。還是會搞錯終止條件和後面要使用 left 或 right。  

為了避免混淆，gemini的建議是：  
1. 堅定使用左閉右開區間 [L,R) 策略 (即 right=len(arr))。  
2. 固定使用 while left < right 作為終止條件。
3. 遵循更新原則：

    - 如果 mid 可能是答案：right=mid

    - 如果 mid 肯定不是答案：left=mid+1  

這樣無論陣列大小，邏輯都是一致的，且最終 left 就會指向您需要的插入點。
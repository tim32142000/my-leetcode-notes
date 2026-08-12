# Binary Search

---

python 模組 bisect  
https://docs.python.org/zh-tw/3/library/bisect.html

---

在 leetcode 162. Find Peak Element，雖然資料沒有排序，還是可以用 binary search。  
題目要找局部最大值，回傳多個解中的一個解就可以，binary search 判斷往左找或往右找。

---

因為看了 labuladong 的書，開始使用左閉右開區間寫 binary search。還是會弄不清楚 while 終止條件和回傳值是 left 或 right。  

labuladong 也有給搜尋區間左閉右閉的程式碼。

為了避免混淆，gemini的建議是：  
1. 堅定使用左閉右開區間 [L,R) 策略 (即 right=len(arr))。  
2. 固定使用 while left < right 作為終止條件。
3. 遵循更新原則：

    - 如果 mid 可能是答案：right=mid

    - 如果 mid 肯定不是答案：left=mid+1  

這樣無論陣列大小，邏輯都是一致的，且最終 left 就會指向您需要的插入點。

---
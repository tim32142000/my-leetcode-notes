# 1733. Minimum Number of People to Teach

https://leetcode.com/problems/minimum-number-of-people-to-teach


## 提示
因為題目是要求計數使用者數量，計算`friendships[i] = [u​​​​​​_i​​​, v​​​​​_​i]`中沒有共通語言的友誼個數不好，記錄不能溝通的使用者有效。

因為只能選一種語言教，要計算每種語言需要被教的人。

Gemini 的程式碼:  
> 找兩個人的共通語言時用 set 比較，先轉換。
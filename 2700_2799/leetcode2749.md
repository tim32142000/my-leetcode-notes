# 2749. Minimum Operations to Make the Integer Zero

https://leetcode.com/problems/minimum-operations-to-make-the-integer-zero

## 想法過程

原本以為加上 $2^i$ 只能消除二進制表示中的一個 bit，運算作用次數要等於數值為1的 bit 個數。  
試誤想到兩個 1 bits 相加是大一位的一個 bit，運算作用次數大於等於剩下 bits 中數值為1的 bit 個數即可。
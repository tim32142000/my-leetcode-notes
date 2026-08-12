# 3514. Number of Unique XOR Triplets II 

https://leetcode.com/problems/number-of-unique-xor-triplets-ii


先用 set_two 存所有可能的兩個數字 xor 結果。再用每一個數字和 set_two 的所有可能作 xor ，得到 set_triplet。

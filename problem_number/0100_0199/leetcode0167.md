# 167. Two Sum II - Input Array Is Sorted

https://leetcode.com/problems/two-sum-ii-input-array-is-sorted


<details>
<summary>解法</summary>
使用 two pointers 放在頭尾， 左右總和太小，左指標+1， 左右總和太大，右指標-1。  
</details>

不用擔心指標移動後有的數字組合沒在程式中執行到。  
總和太小的時候，左指標的數字配上右指標左邊的所有數字總和都太小，因此左指標的數字不可能是答案。


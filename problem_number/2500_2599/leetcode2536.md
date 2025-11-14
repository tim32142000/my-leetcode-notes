# 2536. Increment Submatrices by One

https://leetcode.com/problems/increment-submatrices-by-one

## 解法
使用 2 維的差分陣列和 prefix sum[ [leetcode solution 圖解](https://leetcode.com/problems/increment-submatrices-by-one/solutions/3052675/python3-sweep-line-range-addition-w-visu-7xwq) ]。2 維的差分陣列在左上起始點 +1，正右方和正下方的終點後一格 -1，對角線終點的右下角一個 +1。作 prefix sum 要每一橫列分別從左到右作，再每一直行分別從上到下作。

## 解題過程
有考慮過可能要作下一行使用上一行的 prefix sum，配合巧妙構造的差分陣列能解。別人的解法可以每行每列分開作。
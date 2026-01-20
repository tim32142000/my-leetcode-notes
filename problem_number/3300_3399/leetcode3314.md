# 3314. Construct the Minimum Bitwise Array  

https://leetcode.com/problems/construct-the-minimum-bitwise-array-i

example: nums = [2,3,5,7]  

以下使用二進位：  
10，`ans[i] | ans[i] + 1` ， 0, 1, 2 都不是答案， 3 以上不可能，輸出 -1。  
11，最高位的 1 交給 `ans[i] + 1`，`ans[i]` = 1。  
101，右邊第二位必須為0，靠 + 1 無法到達最高位。 `ans[i]` = 100。  
111，最高位交給 `ans[i] + 1`， `ans[i]` = 11。  

連續 1 的最左邊 1 可以交給 `ans[i] + 1`。找到最左邊 1 的 `shift`， `ans[i] = num - (1 < shift)`。
# 1763. Longest Nice Substring

https://leetcode.com/problems/longest-nice-substring

## 解法
divide and conquer。  
如果發現 `s[i]` 在 `s` 中只有大寫或小寫，則完美字串只可能發生在 `s[:i]` 或 `s[i+1:]`。

`char.swapcase()`：切換大小寫。
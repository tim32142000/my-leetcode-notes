# 1081. Smallest Subsequence of Distinct Characters

https://leetcode.com/problems/smallest-subsequence-of-distinct-characters

這題和 [316. Remove Duplicate Letters
](https://leetcode.com/problems/remove-duplicate-letters) 是同樣的題目。

---

使用 Monotonic Stack ，丟掉可以丟的字典序比較大的字母，存下讓字典序更小的字母。

為了避免 stack 中的字母捨去後就遇不到，先遍歷一次字串，存下字母最後出現的 index。

以及使用 set 檢查，讓 Monotonic Stack 不要存到重複字母。

---
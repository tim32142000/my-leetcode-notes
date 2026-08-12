# 2542. Maximum Subsequence Score

https://leetcode.com/problems/maximum-subsequence-score

雖然題目的搜尋範圍是 subsequence ，可能性很多。

（ A subsequence of indices of an array is a set that can be derived from the set {0, 1, ..., n-1} by deleting some or no elements. ）

但是讓乘數候選清單的 `nums2` 從大到小排序，可以控制 for 迴圈中途 `nums2` subsequence 的最小值。
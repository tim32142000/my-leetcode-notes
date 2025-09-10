# 2327. Number of People Aware of a Secret

https://leetcode.com/problems/number-of-people-aware-of-a-secret

題目的 topic tags 有 Queue，我還沒用到。

## 提示
記錄第`i`天知道的`n[i]`個人、察覺祕密的人數`n_aware`、分享祕密的人數`n_share`。

## 解題過程
初始化 list：發現祕密第`i`天的人有`n[i]`個，作 dp，時間表現不好。目前的迴圈是O(n*forget)<=O($n^2$)，不夠好。  
一天一天更新的`sum(n[delay:forget])`，沒有第一時間想到 sliding window 求和。
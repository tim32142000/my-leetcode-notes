# Prefix Sum

### 快速區間求和

能快速地計算 list 第 i 個元素到第 j 個元素的和。  
`prefix_sum[j] - prefix_sum[i] == sum(list[i:j])`

---

### 處理「絕對值距離之和」問題的核心

計算一個數值為 $x$ 的點到其餘所有數值為 $x$ 的點的距離和，可以簡化。假設數字 $x$ 出現在索引 $[i_1​,i_2​,…,i_k​]$，對於索引 $i_j$​ 的總距離和：  
$$\text{Total Distance} = (i_j \times \text{count}_{\text{left}} - \text{sum}_{\text{left}}) + (\text{sum}_{\text{right}} - i_j \times \text{count}_{\text{right}})$$

---

2-D prefix matrix 題目：  
[1292. Maximum Side Length of a Square with Sum Less than or Equal to Threshold](../problem_number/1200_1299/leetcode1292.md)  
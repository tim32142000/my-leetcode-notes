# 2033. Minimum Operations to Make a Uni-Value Grid  

https://leetcode.com/problems/minimum-operations-to-make-a-uni-value-grid

### 為什麼選擇中位數？ 數線上的兩兩配對法  

想像數線上有許多點，我們要找一個點 k 到所有點的距離和最小。

- **考慮最外側的兩個點 A 和 B**：

  - 如果你把 k 選在 A 與 B 之間的任何位置，點 k 到這兩點的距離之和恆等於 A 到 B 的距離 dist(A,B)。

  - 如果你把 k 選在 A, B 之外，距離之和一定會大於 dist(A,B)。

- **推論**：為了最小化總距離，我們應該把 k 放在最外側這對點的「內部」。

- **遞迴思考**：接下來我們處理次外側的兩點。同樣地，k 必須落在這兩點之間。以此類推，最終 k 必須落在所有點的最中心區域，也就是**中位數**（或是偶數個數時的中位數區間）。
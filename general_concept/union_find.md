# Union Find

## find + 路徑壓縮
```python
def uf_find(x):
    while parents[x] != x:
        parents[x] = parents[parents[x]]
        x = parents[x]
    return x
```
## 將二維座標轉為一維 ID  
```python
def get_id(r, c):
    return r * col + c
```

## 虛擬節點 (Virtual Nodes)：
檢查第一列和最後一列是否連通。建立一個虛擬節點 TOP，連接所有第一列（row 0）的陸地。建立一個虛擬節點 BOTTOM，連接所有最後一列（row R-1）的陸地。  
```python
uf = UnionFind(n + 2) # n+2 用於兩個虛擬節點
TOP = n
BOTTOM = n + 1
```
...  
```python
# 如果是第一列，連到 TOP
if r == 0:
    uf.union(curr_id, TOP)
# 如果是最後一列，連到 BOTTOM
if r == row - 1:
    uf.union(curr_id, BOTTOM)
```

[LeetCode 1970. Last Day Where You Can Still Cross](https://leetcode.com/problems/last-day-where-you-can-still-cross) Hard  
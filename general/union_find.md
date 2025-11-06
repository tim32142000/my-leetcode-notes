# Union Find

find + 路徑壓縮
```python
def uf_find(x):
    while parents[x] != x:
        parents[x] = parents[parents[x]]
        x = parents[x]
    return x
```
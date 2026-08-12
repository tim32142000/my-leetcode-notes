記錄自己低時間效率的 for 迴圈寫法。想法是找完整個 list 都沒找到滿足條件的元素，則答案+1。在 leetcode 上執行時間久。可能是對每個非結尾元素也判斷了 index。

```python
for i in range(n)
    for j in range(n):
        if condition[j]:
            break
        if j == n-1:
            ans += 1
```

改進方式：

```python

for i in range(n)
    found = False
    for j in range(n):
        if condition[j]:
            found = True
            break

    if not found:
        ans += 1

```
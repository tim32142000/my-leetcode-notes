# Backtracking

全排列 (Permutations) 範例

```python
def backtrack(path, used):
    if len(path) == n:
        res.append(path[:]) # 複製一份放入結果
        return
    
    for i in range(len(nums)):
        if not used[i]:
            # 1. 做選擇 (修改狀態)
            used[i] = True
            path.append(nums[i])
            
            # 2. 遞迴
            backtrack(path, used)
            
            # 3. 撤銷操作 (還原狀態)
            path.pop()       # 把剛剛加進去的元素拿出來
            used[i] = False  # 把標記改回 False
```

注意 `res.append(path[:])` 的 `path[:]` 要有方括號和冒號。 `append(path)`，會 append 空 list。
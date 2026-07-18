# Trie

## dict 寫法

`strs1` is list of strings

```python
trie = {}        

for s1 in strs1:
    curr = trie
    for char in s1:
        if char not in curr:
            curr[digit] = {}
        curr = curr[digit]
```

---

## collections.defaultdict 寫法

利用內建的 collections.defaultdict 寫出多層巢狀字典：
```python
import collections

# 這行宣告了一個可以多層套娃的字典結構
Trie = lambda: collections.defaultdict(Trie)

# 實戰使用：
root = Trie()

# 插入 "cat"
current = root
for char in "cat":
    # 甚至不用檢查 char 在不在，defaultdict 會自動幫你建立下一層字典！
    current = current[char]
current['#'] = True
```
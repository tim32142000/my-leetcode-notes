# Itertools

## accumulate
### 設定初始值
```python
import itertools
data = [1, 2, 3]
result = list(itertools.accumulate(data, initial=100)) # output: [100,101,103,106]
```


## 參考資料
[官方文檔](https://docs.python.org/zh-tw/3/library/itertools.html)
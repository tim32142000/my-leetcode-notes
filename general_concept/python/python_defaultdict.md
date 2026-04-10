# Python defaultdict()

在 `defaultdict` 中，傳入的必須是一個「可呼叫對象（Callable）」。當我們需要為建構函式帶入參數（如 `maxlen=2`）時，透過 `lambda` 建立一個匿名函式是 Python 最標準且優雅的作法。

---

## `defaultdict(lambda: deque(maxlen=2))`

### 為什麼這裡一定要用 `lambda`？

`defaultdict` 的運作原理是：當你存取一個不存在的 Key 時，它會呼叫你提供的那個物件來產生預設值。

#### 錯誤寫法： `defaultdict(deque(maxlen=2))`

這會先執行 `deque(maxlen=2)` 產生一個物件，然後嘗試把這個「物件實例」當成工廠函式。這會拋出 `TypeError`，因為 deque 物件本身不可呼叫。

#### 正確寫法： `defaultdict(lambda: deque(maxlen=2))`

這傳入的是一個函式。每當遇到新 Key，`defaultdict` 就執行一次這個 `lambda`，回傳一個全新的、限制長度為 2 的 `deque`。

---

## 其他常見的 `defaultdict` 進階技巧

除了 `lambda`，你也可以根據需求使用不同的工廠函式：

### 1. 設定固定的預設數值

如果你希望預設值不是 `0`（`int`），而是 `100`：

```python
d = defaultdict(lambda: 100)
```

### 2. 巢狀字典 (Nested Dictionary)

這在處理複雜資料結構（如實作圖論的鄰接表）時非常有用：

```python
# 建立一個自動產生字典的字典
matrix = defaultdict(dict) 
# 或是更深層的
deep_tree = defaultdict(lambda: defaultdict(list))
```

### 3. 使用自定義函式

如果邏輯太複雜，不一定要用 `lambda`，也可以定義正規函式：

```python
def factory():
    # 可以在這裡做更多初始化邏輯
    return deque(maxlen=2)

d = defaultdict(factory)
```

---

#### 溫馨小提示

在使用 `defaultdict(lambda: deque(maxlen=2))` 時，有一點要特別注意：當你「讀取」一個不存在的 Key（例如 `print(history[999])`），`defaultdict` 會自動把這個 Key 建立起來。

在某些演算法題中，如果之後有遍歷 `history.keys()` 的需求，這些「因為讀取而產生的空白 Key」可能會影響結果。
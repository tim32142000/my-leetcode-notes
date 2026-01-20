# Python int

## Python 處理 32 位元有號數

$-2^{31}$ <= result <= $2^{31} - 1$
```python
# Python 負數處理：
# 數字是 32 位元有號數，範圍是 -2^31 到 2^31-1
# 第 31 位是 1，代表它是負數
if result >= 2**31:
    result -= 2**32
```
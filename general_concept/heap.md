#Heap

- heap 存的資料需要更新而影響排序的話。直接改寫heap 中元素再重新排序效率比較低。更有效率的方法：push 新元素進 heap，使用另一變數存最新版訊息，檢驗 heap 頂端的元素是最新的或是不可用的。（[2353. Design a Food Rating System](../problem_number/2300_2399/leetcode2353.md)）


---
### Max Heap 方案
```python
import heapq

class MaxHeap:
    def __init__(self): self.h = []
    def push(self, val): heapq.heappush(self.h, -val)
    def pop(self): return -heapq.heappop(self.h)
    def peek(self): return -self.h[0]
```
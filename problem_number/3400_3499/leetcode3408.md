# 3408. Design Task Manager

https://leetcode.com/problems/design-task-manager

## 提示

[2353. Design a Food Rating System](../2300_2399/leetcode2353.md) 再進一步的題目。用 heap 排序，用其他變數驗證 heap 中元素是最新版本或是被編輯、被刪除的版本。heap 頂端的元素只使用一次就刪除是和題目 2353. 的不同之處。作`void rmv(int taskId)`和`int execTop()`要把驗證用的元素刪除乾淨，避免和更之後的訊息混在一起。  

C++的 set 可直接使用，常駐排序，有快速刪除元素和插入元素的功能。  

python 使用 SortedList。第三方套件，可能需要安裝。  
```python
from sortedcontainers import SortedList
```
[關於python類SortedList詳解 python 程式碼](https://www.templatestood.com/11/04/%E9%97%9C%E6%96%BCpython%E9%A1%9Esortedlist%E8%A9%B3%E8%A7%A3-python-%E7%A8%8B%E5%BC%8F%E7%A2%BC/)  
[Python中 SortedList的用法](https://blog.csdn.net/qqrrjj2011/article/details/138843151)
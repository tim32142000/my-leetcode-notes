# 162. Find Peak Element

https://leetcode.com/problems/find-peak-element

Constraint 保證了相鄰元素不相等， `nums[i] != nums[i + 1]` for all valid `i`. 

 `nums[mid]` 和 `nums[mid+1]` 比較就可以知道 peak 發生在哪一邊。  
`nums[mid]>nums[mid+1]`，peak 發生在 mid 或左邊。  
`nums[mid]<nums[mid+1]`，peak 發生在右邊。  

題目設定頭尾的元素比邊界外還大。持續增加到邊界也會產生 peak。  

只比較 `nums[mid]` 和 `nums[mid + 1]`，可以確保不會出界。  
`left = 0, right = 1` 的時候 `mid = 0`，去取 `nums[mid-1]`會取到 -1 index。

```python
while left < right:
    mid = left + (right - left) // 2
    if nums[mid] < nums[mid + 1]:
        left = mid + 1
    else:
        right = mid
```
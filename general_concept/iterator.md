
- 逐個取出元素時使用`iter_data = iter(processed_list)`，取出時`ans.append(next(iter_data))`。存 iterator，有時省下存 list 的記憶體。
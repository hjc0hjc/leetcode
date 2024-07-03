# 字符串
字符串长度不用先转化为list，但是遍历每个字符需要list(s)

```
if len(s) % 2 == 1:
  return False
for i in list(s):
  print(*i.encode())
```

# 字符串

* 字符串长度不用先转化为list，遍历字符串的每个字符也不需要list(s)

**有效的括号**

```
class Solution:
    def isValid(self, s: str) -> bool:
        if len(s) % 2 == 1: # 直接len即可
            return False
        dic = {"}":"{", "]":"[", ")":"("}
        ans = [] # 栈
        for i in s: # 不用转化str为list
            if i in ("(","[",'{'):
                ans.append(i)
            else: # 这里也可以挪到if位置，用i in dic进行判断
                if ans == [] or ans[-1] != dic[i]:
                    return False
                ans.pop(-1) # 因为前边return过了，这里不用else
        return not ans # 空栈可以直接用not识别
```




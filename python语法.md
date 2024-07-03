# 字符串

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
* 字符串长度不用先转化为list，遍历字符串的每个字符也不需要list(s)

**哈沙德数**

```
x, s = divmod(x, 10)
```
```
return -1 if x % s else s
```
```
s = sum(map(int,str(x)))
```
* 计算整数各位的数字和：不断除10，不断取余。注意divmod可以一次性获得商、余
* 另外，**条件表达式/三元操作符**，用法：返回1如果cond否则返回2
* 另外，map用法：把第二个参数【可迭代对象】的每个元，当作参数传入第一个参数【函数】，得到新的可迭代对象


# 树

树一般是用链表的形式存储的，一个节点有val、left、right三个参数。
注意，如果节点为空，则不能访问这三个参数，反之叶子结点可以访问，只不过right和left的结果是None。
因此，在对树进行操作时，往往在开头加上判断：if root: 或者while root: 

* 前序中序啥的遍历：用栈
* 层的遍历，广度优先的算法，也就是一层一层输出层的全部：用队列

**对称二叉树**

```
if not root1 or not root2 or root1.val != root2.val:
    return False
```
* 节点首先有存在性，然后有值，可以用一句话对应多种情况，这样不会因为节点是None访问val报错
* 另外，这里不能直接使用if node1 != node2进行判断，因为对对象（也就是指针之类的）进行相等判断是判断存储地址是否一致，而不是值














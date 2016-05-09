##4.2. for 语句
Python 中的 for 语句和 C 或 Pascal 中的略有不同。通常的循环可能会依据一个等差数值步进过程(如 Pascal)，或由用户来定义迭代步骤和中止条件(如 C )，Python 的 for 语句依据任意序列(链表或字符串)中的子项，按它们在序列中的顺序来进行迭代。例如(没有暗指):
```bash
>>> # Measure some strings:
... words = ['cat', 'window', 'defenestrate']
>>> for w in words:
... print w, len(w)
...
cat 3
window 6
defenestrate 12
```
在迭代过程中修改迭代序列不安全(只有在使用链表这样的可变序列时才会有这样的情况)。如果你想要修改你迭代的序列(例如：复制选择项)，你可以迭代它的复本。使用切割标识就可以很方便地做到这一点:
```bash
>>> for w in words[:]: # Loop over a slice copy of the entire list.
... if len(w) > 6:
... words.insert(0, w)
...
>>> words
['defenestrate', 'cat', 'window', 'defenestrate']
```

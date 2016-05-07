##4.1. if 语句
也许最有名的是 if 语句。例如:
```bash
>>> x = int(raw_input("Please enter an integer: "))
Please enter an integer: 42
>>> if x < 0:
... x = 0
... print 'Negative changed to zero'
... elif x == 0:
... print 'Zero'
... elif x == 1:
... print 'Single'
... else:
... print 'More'
...
More
```
可能会有零到多个 elif 部分，else 是可选的。关键字 elif 是 “else if” 的缩写，这个可以有效避免过深的缩进。if ... elif ... elif ... 序列用于替代其它语言中的 switch 或 case 语句。

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
##4.3. range() 函数
如果你需要一个数值序列，内置函数 range() 会很方便，它生成一个等差级数链表:
```bash
>>> range(10)
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
range(10) 生成了一个包含 10 个值的链表，它用链表的索引值填充了这个长度为 10 的列表，所生成的链表中不包括范围中的结束值。也可以让 range 操作从另一个数值开始，或者可以指定一个不同的步进值(甚至是负数，有时这也被称为 “步长”):
```bash
>>> range(5, 10)
[5, 6, 7, 8, 9]
>>> range(0, 10, 3)
[0, 3, 6, 9]
>>> range(-10, -100, -30)
[-10, -40, -70]
```
需要迭代链表索引的话，如下所示结合使用 range() 和 len():
```bash
>>> a = ['Mary', 'had', 'a', 'little', 'lamb']
>>> for i in range(len(a)):
... print i, a[i]
...
0 Mary
1 had
2 a
3 little
4 lamb
```
不过，这种场合可以方便地使用 enumerate()，请参见 循环技巧。

##4.4. break 和 continue 语句, 以及循环中的 else 子句
break 语句和 C 中的类似，用于跳出最近的一级 for 或 while 循环。

循环可以有一个 else 子句；它在循环迭代完整个列表 (对于 for) 后或执行条件为 false (对于 while) 时执行，但循环被 break 中止的情况下不会执行。以下搜索素数的示例程序演示了这个子句:
```bash
>>> for n in range(2, 10):
... for x in range(2, n):
... if n % x == 0:
... print n, 'equals', x, '*', n/x
... break
... else:
... # loop fell through without finding a factor
... print n, 'is a prime number'
...
2 is a prime number
3 is a prime number
4 equals 2 * 2
5 is a prime number
6 equals 2 * 3
7 is a prime number
8 equals 2 * 4
9 equals 3 * 3
```
(Yes, 这是正确的代码。看仔细: else 语句是属于 for 循环之中, 不是 if 语句。)

与循环一起使用时，else 子句与 try 语句的 else 子句比与 if 语句的具有更多的共同点：try 语句的 else 子句在未出现异常时运行，循环的 else 子句在未出现 break 时运行。更多关于 try 语句和异常的内容，请参见 异常处理。

continue 语句是从 C 中借鉴来的，它表示循环继续执行下一次迭代:
```bash
>>> for num in range(2, 10):
... if num % 2 == 0:
... print "Found an even number", num
... continue
... print "Found a number", num
Found an even number 2
Found a number 3
Found an even number 4
Found a number 5
Found an even number 6
Found a number 7
Found an even number 8
Found a number 9
```

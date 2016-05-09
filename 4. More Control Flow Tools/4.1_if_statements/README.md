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


# 第七章: 文件
- [第七章: 文件](#第七章-文件)
	- [创建](#创建)
	- [用法](#用法)
		- [序列读取](#序列读取)
		- [整个文件读取](#整个文件读取)
	- [扩展](#扩展)
	- [练习](#练习)

## 创建
句柄`handle`由函数`open()`创建。
```Python
handle = open(filename, mode)
```

|   模式    |                                   描述                                   |
|:---------:|:------------------------------------------------------------------------:|
| r（默认） |                以只读方式打开文件，指针将会放在文件的开头             |
|     w     | 打开一个文件只用于写入，并从开头开始编辑，如果该文件不存在，创建新文件。 |
**Example:**
```python
fhand = open('mbox.txt')
```
句柄`handle`:
```
<_io.TextIOWrapper name='mbox.txt' mode='r' encoding='UTF-8'>
```
## 用法
示例文件 `this.txt`:
```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
...
```
计算机中，文本文件的每行末尾都有换行符（newline）`\n`。
```
The Zen of Python, by Tim Peters\n
\n
Beautiful is better than ugly.\n
Explicit is better than implicit.\n
Simple is better than complex.\n
Complex is better than complicated.\n
...
```

### 序列读取
文件中的每一行都是字符串，所以字符串共同构成**序列**。
* 有多少行，就有多少个字符串
* 序列存在先后顺序

```Python
xfile = open('this.txt')
for cheese in xfile:
    print(cheese)
```

**注：** 每一个字符串的末尾是换行符`\n`，同时`print()`也会自动换行，因此打印出来的字符串之间会空一行。
```
The Zen of Python, by Tim Peters



Beautiful is better than ugly.

Explicit is better than implicit.

Simple is better than complex.

Complex is better than complicated.
...
```

### 整个文件读取
将整个文件读入**一个字符串**。
```Python
fhand = open('this.txt')
inp = fhand.read()
print(inp)
```

```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
...
```

## 扩展
`open()`之后需要`close()`:
```Python
fhand = open('this.txt')
fhand.close()
```
但常于`with`连用，可不用进行`close()`操作。
```Python
with open('this.txt') as fhand:
    print(fhand.read())
```

## 练习
读取`this.txt`的前5行。
```Python
with open('this.txt') as fhand:
    inp = fhand.read().split('\n')
    for i in inp[:5]:
        print(i)
```

```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
```

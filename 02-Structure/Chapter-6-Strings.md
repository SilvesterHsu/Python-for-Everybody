# 第六章: 字符串
- [第六章: 字符串](#第六章-字符串)
	- [创建](#创建)
	- [用法](#用法)
		- [字符串连接](#字符串连接)
		- [字符串转换](#字符串转换)
		- [字符串选择](#字符串选择)
			- [选择](#选择)
			- [切片](#切片)
		- [字符串长度](#字符串长度)
		- [逻辑判断](#逻辑判断)
		- [比较](#比较)
		- [字符查找](#字符查找)
		- [抹掉空格](#抹掉空格)
		- [字符串字典](#字符串字典)

## 创建
`string`可由单双引号创建，`''` 或 `""`。
```python
str1 = 'Hello'
str2 = "World"
```
## 用法
### 字符串连接
使用 `+` 来连接2个字符串。
```Python
>>> str1 = 'Hello'
>>> str2 = "World"
>>> str1+str2
'HelloWorld'
```
### 字符串转换
通过 `int()` 将 `string ` 转换为 `int` 类。
```Python
>>> str3 = '123'
>>> type(str3)
<class 'str'>
>>> num = int(str3)
>>> type(num)
<class 'int'>
```

> `int()` 常于 `input()` 连用。
> ```python
> >>> num = int(input('number = '))
> number = 123
> >>> type(num)
> <class 'int'>
> ```

**Example:** $output = input + 1$
```Python
>>> x = input("number = ") + 1
number = 123
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str
```
```Python
>>> x = input("number = ")
number = 123
>>> x = int(x) + 1
>>> x
124
```
### 字符串选择
#### 选择
通过索引 `index` 和方括号 `[ ]` 来查看字符串内部数据。
```Python
>>> fruit = 'banana'
>>> index = 1
>>> fruit[index]
'a'
```
* `index` 必须为整数
* `index` 必须从 `0` 开始
* `index` 可以是运算操作
  ```Python
  >>> fruit = 'banana'
  >>> fruit[2-1]
  'a'
  ```

> 如果索引 `index` 超出字符串长度，将会导致错误。
> ```python
> >>> fruit = 'banana'
> >>> fruit[10]
> Traceback (most recent call last):
>   File "<stdin>", line 1, in <module>
> IndexError: string index out of range
> ```

#### 切片
```Python
>>> s = 'Monty Python'
>>> print(s[0:4])
Mont
```
* 切片位置到第二个数之前，不包括第二个数。
  ```Python
  >>> print(s[6:7])
  P
  ```
* 如果索引超出范围，切片会在字符串末尾结束。
  ```Python
  >>> print(s[6:20])
  Python
  ```
* 左、右缺省将被分别视作从头开始和到末尾结束。
  ```python
  >>> s = 'Monty Python'
  >>> print(s[:2])
  Mo
  >>> print(s[8:])
  thon
  >>> print(s[:])
  Monty Python
  ```

### 字符串长度
内建函数 `len()` 可用来计算字符串长度。
```Python
>>> fruit = 'banana'
>>> print(len(fruit))
6
```
### 逻辑判断
```Python
>>> fruit = 'banana'
>>> 'n' in fruit
True
>>> 'm' in fruit
False
>>> 'nan' in fruit
True
>>> if 'a' in fruit :
...     print('Found it!')
...
Found it!
```
### 比较
```Python
if word == 'banana':
    print('All right, bananas.')

if word < 'banana':
    print('Your word,' + word + ', comes before banana.')
elif word > 'banana':
    print('Your word,' + word + ', comes after banana.')
else:
    print('All right, bananas.')
```
### 字符查找
我们通过 `find()` 来寻找字符串中的子字符串。
* find() 寻找子字符串第一次出现的位置。
  ```Python
  >>> fruit = 'banana'
  >>> pos = fruit.find('na')
  >>> print(pos)
  2
  ```
* 如果子字符串未被找到，则 `find()` 返回 `-1`。
  ```Python
  >>> aa = fruit.find('z')
  >>> print(aa)
  -1
  ```
### 抹掉空格
* `strip()` 同时抹掉开头和结尾的空格（子字符串）。
  ```Python
  >>> greet = '   Hello Bob  '
  >>> greet.strip()
  'Hello Bob'
  ```
* `lstrip()` 和 `rstrip()` 分别抹掉开头和结尾的空格（子字符串）。
  ```Python
  >>> greet = '   Hello Bob  '
  >>> greet.lstrip()
  'Hello Bob  '
  >>> greet.rstrip()
  '   Hello Bob'
  ```

### 字符串字典
字符串内建函数库 [Library](https://docs.python.org/3/library/stdtypes.html#string-methods).
```Python
>>> stuff = 'Hello world'
>>> type(stuff)
<class 'str'>
>>> dir(stuff)
['capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
```

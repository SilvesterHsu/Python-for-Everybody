# 第八章: 列表
- [第八章: 列表](#第八章-列表)
	- [创建](#创建)
	- [用法](#用法)
		- [数据选择](#数据选择)
		- [连接](#连接)
		- [长度](#长度)
		- [切片](#切片)
		- [逻辑](#逻辑)
		- [排序](#排序)
		- [常用内建函数](#常用内建函数)
		- [字典](#字典)
	- [附加](#附加)
		- [列表与字符串](#列表与字符串)

## 创建
列表用于存储和修改数据，并通过`[` `]`来创建。
```Python
L = [1, 24, 76]
```
* 列表中可录入任何python数据类型
  ```Python
  L_1 = [1, 24, 76]
  L_2 = ['red', 'yellow', 'blue']
  ```

* 列表可以为空
  ```Python
  L_3 = []
  ```

* 列表内容有序
  ```Python
  L = [1, 24, 76]
  ```

## 用法
### 数据选择
列表和字符串相同，通过索引`index`进行选取。
```Python
friends = [ 'Joseph', 'Glenn', 'Sally' ]
print(friends[1])
```
```Python
Glenn
```
与`string`相比，`string`内部数据不能改变，而`list`可以改变内部数据
* 修改`string`数据
  ```Python
  fruit = 'Banana'
  fruit[0] = 'b'
  ```

  ```
  ---------------------------------------------------------------------------
  TypeError                                 Traceback (most recent call last)
  <ipython-input-2-2bc78b004470> in <module>
        1 fruit = 'Banana'
  ----> 2 fruit[0] = 'b'

  TypeError: 'str' object does not support item assignment
  ```

* 修改`list`数据
  ```Python
  lotto = [2, 14, 26, 41, 63]
  print(lotto)
  lotto[2] = 28
  print(lotto)
  ```

  ```
  [2, 14, 26, 41, 63]
  [2, 14, 28, 41, 63]
  ```

### 连接
使用 `+` 来连接2个列表。
```Python
a = [1, 2, 3]
b = [4, 5, 6]
c = a + b
print(c)
```
```
[1, 2, 3, 4, 5, 6]
```

### 长度
内建函数 `len()` 可用来计算列表长度。
```Python
x = [ 1, 2, 'joe', 99]
print(len(x))
```
```
4
```

### 切片
与`string`相同
```python
t = [9, 41, 12, 3, 74, 15]
t[1:3]
```
```
[41, 12]
```
**注：** 切片位置到第二个数之前，不包括第二个数。
```Python
t = [9, 41, 12, 3, 74, 15]
t[:4]
```
```
[9, 41, 12, 3]
```
### 逻辑
```Python
some = [1, 9, 21, 10, 16]
9 in some
```
```
True
```
```Python
15 in some
```
```
False
```
```Python
20 not in some
```
```
True
```
### 排序
列表内部数据有序，且可以排序。
```Python
friends = [ 'Joseph', 'Glenn', 'Sally' ]
friends.sort()
print(friends)
```
```
['Glenn', 'Joseph', 'Sally']
```
### 常用内建函数
* `len()`:
  ```Python
  nums = [3, 41, 12, 9, 74, 15]
  print(len(nums))
  ```

  ```
  6
  ```

* `max()`:
  ```Python
  print(max(nums))
  ```

  ```
  74
  ```

* `min()`:
  ```Python
  print(min(nums))
  ```

  ```
  3
  ```

* `sum()`:
  ```Python
  print(sum(nums))
  ```

  ```
  154
  ```

### 字典
列表内建函数库[Library](http://docs.python.org/tutorial/datastructures.html)。
```Python
x = list()
type(x)
```
```
list
```
```Python
dir(x)
```
```
['__add__',
 '__class__',
 '__contains__',
 '__delattr__',
 '__delitem__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__getitem__',
 '__gt__',
 '__hash__',
 '__iadd__',
 '__imul__',
 '__init__',
 '__init_subclass__',
 '__iter__',
 '__le__',
 '__len__',
 '__lt__',
 '__mul__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__reversed__',
 '__rmul__',
 '__setattr__',
 '__setitem__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 'append',
 'clear',
 'copy',
 'count',
 'extend',
 'index',
 'insert',
 'pop',
 'remove',
 'reverse',
 'sort']
```
## 附加
### 列表与字符串
`split`可以将字符串分成几部分并生成字符串列表。
```Python
abc = 'With three words'
abc.split()
```
```
['With', 'three', 'words']
```

# 第九章: 字典
- [第九章: 字典](#第九章-字典)
	- [创建](#创建)
	- [用法](#用法)
		- [数据选择](#数据选择)
			- [Python新旧](#python新旧)
			- [获取 `Key`](#获取-key)
			- [获取 `Value`](#获取-value)
			- [获取一对数据 `items`](#获取一对数据-items)
		- [逻辑](#逻辑)
		- [计数](#计数)
			- [通常](#通常)
			- [字典内置函数`get()`](#字典内置函数get)
			- [找出最大值](#找出最大值)

## 创建
字典用于存储和修改数据，并通过`{` `}`来创建，与`list`不同，我们不再像`list`一样使用`index`来访问内部元素，而使用`Key`来给每个数据打上标签，因此`dict`需要同时存储1对值，`Key`和`Value`，同时`Key`必须是`string`类型。
```Python
D = {Key: Value}
```
```Python
D = {'money': 12, 'tissues': 75, 'candy': 3}
```
空字典可以通过`[` `]`来添加数据。
```Python
D = dict()
D['money'] = 12
D['tissues'] = 75
D['candy'] = 3
```
* 列表中可录入任何python数据类型
  ```Python
  >>> L_1 = [1, 24, 76]
  >>> L_2 = [3, 75, 12]
  >>> D_1 = {'list_1': L_1,'list_2': L_2}
  >>> D_1
  {'list_1': [1, 24, 76], 'list_2': [3, 75, 12]}
  >>> D_2 = {'list_1': L_1,'dict_1': D_1}
  >>> D_2
  {'list_1': [1, 24, 76], 'dict_1': {'list_1': [1, 24, 76], 'list_2': [3, 75, 12]}}
  ```

* 字典可以为空
  ```Python
  D_3 = {}
  ```

	或者
	```Python
	D_3 = dict()
	```

* 字典内容无序
  ```Python
  >>> D_4 = { 'chuck' : 1 , 'fred' : 42, 'jan': 100}
  >>> print(D_4)
  {'jan': 100, 'chuck': 1, 'fred': 42}
  ```

## 用法
### 数据选择
通过索引`Key`进行选取。
```Python
>>> D = {'money': 12, 'tissues': 75, 'candy': 3}
>>> print(D['tissues'])
75
```

#### Python新旧
Python更新3.4后，`keys()`不再返回`list`类型，而是使用一种可迭代类型`dict_keys`
```Python
>>> D = {'money': 12, 'tissues': 75, 'candy': 3}
>>> D.keys()
dict_keys(['money', 'tissues', 'candy'])
```
该效果同样作用于`values()`和`items()`。

|    函数     |   返回类型    |                             示例                             |
|:-----------:|:-------------:|:------------------------------------------------------------:|
|  .keys()  |  dict_keys  |          dict_keys(['money', 'tissues', 'candy'])         |
| .valuse() | dict_values |                  dict_values([12, 75, 3])                  |
| .items()  | dict_items  | dict_items([('money', 12), ('tissues', 75), ('candy', 3)]) |

#### 获取 `Key`
```Python
>>> D = {'money': 12, 'tissues': 75, 'candy': 3}
>>> list(D.keys())
['money', 'tissues', 'candy']
```
或者
```Python
>>> D = {'money': 12, 'tissues': 75, 'candy': 3}
>>> list(D)
['money', 'tissues', 'candy']
```

#### 获取 `Value`
```Python
>>> D = {'money': 12, 'tissues': 75, 'candy': 3}
>>> list(D.values())
[12, 75, 3]
```

#### 获取一对数据 `items`
```Python
>>> D = {'money': 12, 'tissues': 75, 'candy': 3}
>>> list(D.items())
[('money', 12), ('tissues', 75), ('candy', 3)]
```
**Example:**
```Python
>>> D = {'money': 12, 'tissues': 75, 'candy': 3}
>>> for k, v in D.items():
...     print(k,v)
...
money 12
tissues 75
candy 3
```

### 逻辑
`in`的查找功能在字典中作用于`Key`。
```Python
>>> D = {'money': 12, 'tissues': 75, 'candy': 3}
>>> 'tissues' in D
True
>>> 75 in D
False
```
**Example:**
循环中的`key`从字典的`Key`中取值。
```Python
>>> counts = { 'chuck' : 1 , 'fred' : 42, 'jan': 100}
>>> for key in counts:
...     print(key, counts[key])
...
chuck 1
fred 42
jan 100
```

### 计数
字典常用来计数。
#### 通常
**计数：**
```Python
counts = dict()
names = ['csev', 'cwen', 'csev', 'zqian', 'cwen']
for name in names :
    if name not in counts:
       counts[name] = 1
    else :
        counts[name] = counts[name] + 1
print(counts)
```
```Python
{'csev': 2, 'cwen': 2, 'zqian': 1}
```

#### 字典内置函数`get()`
**函数说明：**
`get()`函数用于获取`Value`，不会抛出`error`。
`D.get(Key, DefaultValue)`：如果在字典`D`中存在`Key`，则`pass`，如果不存在，则返回初值`DefaultValue`。
```Python
>>> D = { 'chuck' : 1 , 'fred' : 42, 'jan': 100}
>>> D.get('fred',0)
42
>>> D.get('frd',13)
13
```
**计数：**
```Python
counts = dict()
names = ['csev', 'cwen', 'csev', 'zqian', 'cwen']
for name in names :
    counts[name] = counts.get(name, 0) + 1
print(counts)
```
```Python
{'csev': 2, 'cwen': 2, 'zqian': 1}
```

#### 找出最大值
```Python
bigcount = None
bigword = None
for word,count in counts.items():
    if bigcount is None or count > bigcount:
        bigword = word
        bigcount = count
print(bigword,bigcount)
```

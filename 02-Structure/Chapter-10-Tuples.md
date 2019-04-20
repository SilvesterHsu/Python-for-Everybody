# 第10章: 元组
- [第10章: 元组](#第10章-元组)
	- [创建](#创建)
	- [用法](#用法)
		- [排序](#排序)

## 创建
列表用于存储和修改数据，并通过`(` `)`来创建。
```Python
>>> T = ('Glenn', 'Sally', 'Joseph')
>>> T[2]
'Joseph'
```

与`string`类型相似，你无法修改其内部数据
```Python
>>> T[2] = 'Jim'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

**优点：**
* 内存使用更少
* 执行效率更高

> 临时变量通常使用`tuple`

## 用法
### 排序
排序使用`sorted`函数
```Python
sorted(iterable, /, *, key=None, reverse=False)
```

**Example:**
```Python
>>> c = {'a':10, 'b':1, 'c':22}
>>> tmp = list()
>>> for k, v in c.items() :
...     tmp.append( (v, k) )
...
>>> print(tmp)
[(10, 'a'), (22, 'c'), (1, 'b')]
>>> tmp = sorted(tmp, reverse=True)
>>> print(tmp)
[(22, 'c'), (10, 'a'), (1, 'b')]
```

可用来筛选出现频率最高的前几个类。

# Chapter 6: Strings
- [Chapter 6: Strings](#chapter-6-strings)
	- [Creation](#creation)
	- [Usages](#usages)
		- [String connection](#string-connection)
		- [String Converting](#string-converting)
		- [String Selection](#string-selection)
			- [Selection](#selection)
			- [Slicing](#slicing)
		- [String Length](#string-length)
		- [Logical Operator](#logical-operator)
		- [String Comparison](#string-comparison)
		- [Searching a String](#searching-a-string)
		- [Stripping Whitespace](#stripping-whitespace)
		- [String Library](#string-library)

## Creation
`string` could be created by `''` or `""`.
```Python
str1 = 'Hello'
str2 = "World"
```
## Usages
### String connection
Use `+` to conect two trings.
```Python
>>> str1 = 'Hello'
>>> str2 = "World"
>>> str1+str2
'HelloWorld'
```
### String Converting
Use `int()` to convert a `string ` into a `int` value.
```Python
>>> str3 = '123'
>>> type(str3)
<class 'str'>
>>> num = int(str3)
>>> type(num)
<class 'int'>
```

> This function is commonly used with `input()`.
> ```python
> >>> num = int(input('number = '))
> number = 123
> >>> type(num)
> <class 'int'>
> ```

**Example:** input a number and get a number one greater than the input.
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
### String Selection
#### Selection
Use `index` and `[ ]` to look inside strings.
```Python
>>> fruit = 'banana'
>>> index = 1
>>> fruit[index]
'a'
```
* `index` must be a integer
* `index` must start from `0`
* `index` can be an expression that is computed
  ```Python
  >>> fruit = 'banana'
  >>> fruit[2-1]
  'a'
  ```

> You will get a python error if you attempt to index beyond the end of a string
> ```python
> >>> fruit = 'banana'
> >>> fruit[10]
> Traceback (most recent call last):
>   File "<stdin>", line 1, in <module>
> IndexError: string index out of range
> ```

#### Slicing
```Python
>>> s = 'Monty Python'
>>> print(s[0:4])
Mont
```
* The second number is one beyond the end of the slice - “up to but not including”
  ```Python
  >>> print(s[6:7])
  P
  ```
* If the second number is beyond the end of the string, it stops at the end
  ```Python
  >>> print(s[6:20])
  Python
  ```
* vacant is assumed to be the beginning or end of the string respectively
  ```python
  >>> s = 'Monty Python'
  >>> print(s[:2])
  Mo
  >>> print(s[8:])
  thon
  >>> print(s[:])
  Monty Python
  ```

### String Length
The built-in function `len()` gives the length of a string.
```Python
>>> fruit = 'banana'
>>> print(len(fruit))
6
```
### Logical Operator
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
### String Comparison
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
### Searching a String
We use the `find()` function to search for a substring within another string.
* find() finds the first occurrence of the substring
  ```Python
  >>> fruit = 'banana'
  >>> pos = fruit.find('na')
  >>> print(pos)
  2
  ```
* If the substring is not found, find() returns -1
  ```Python
  >>> aa = fruit.find('z')
  >>> print(aa)
  -1
  ```
### Stripping Whitespace
* `strip()` removes both beginning and ending whitespace
  ```Python
  >>> greet = '   Hello Bob  '
  >>> greet.strip()
  'Hello Bob'
  ```
* `lstrip()` and `rstrip()` remove whitespace at the left or right
  ```Python
  >>> greet = '   Hello Bob  '
  >>> greet.lstrip()
  'Hello Bob  '
  >>> greet.rstrip()
  '   Hello Bob'
  ```

### String Library
String also has in-built [Library](https://docs.python.org/3/library/stdtypes.html#string-methods).
```Python
>>> stuff = 'Hello world'
>>> type(stuff)
<class 'str'>
>>> dir(stuff)
['capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
```

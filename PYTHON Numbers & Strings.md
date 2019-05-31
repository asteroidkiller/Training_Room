# PYTHON 溫習筆記 (1) Numbers & Strings

### Numbers

> Types of Numbers

1. Integers
2. Floating-point number

----
> Basic Arithmetic (Division)

1. floor division
   
   1. 7//4 = 1
2. modulo
   
   1. 7%4 = 3

----
>Variable Assignment (Rules)
1. names can not contain spaces, or some symbols, use _intead
   
2. names can not start with a number 

3. best practice (PEP8) that names are lowercase with underscores

4. avoid use l (lowercase letter,el) and I (uppercse letter, eye) as they can be confused with 1 and 0

----



### Strings

Use single quotes or double quotes to create a String

```python
print('\n can be used to print a new line')
```
```python
len('Hello world')
```
\n 可以隔行

Len計算String的字數



_**String Indexing**_   ('Hello World'例子)

以'Hello World'為例0=H, 1=e, 2=l, 3=l, 4=o 5=空格 如此類推

```python
s[1:] #grab everything after the first term
```

'ello World'

```python
s[:3] #grab everything up to 3rd index
```

'Hel'

```python
s[:] #grab everything
```

'Hello World'

```python
s[-1] #Last letter
```

'd'

```python
s[:-1] #grab everything but the last letter
```

'Hello Worl'

```python
s[::1] #grab everything but go in steps size of 1
```

'Hello World'

```python
s[::2] #grab everything but go in steps size of 2
```

'HloWrd'

```python
s[::-1] #use this to print a string backwards
```

'dlroW olleH'

```
letter='z'
letter*6
'zzzzzz'
```

字元重複寫入6次

```
s.upper() #改全部大寫

s.lower() #改全部小寫

s.split() # Split by a specific element
```



----

### Lists

### Dictionaries

### Tuples

### Sets

### Booleans






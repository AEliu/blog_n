---
title: 关于Python的记录
urlname: about-python 
date: 2020-02-04 10:27:21
tags:
- IT
- Python
---

随时记录以备查。

<!-- more -->

## Python 的安装

to be continue

## 资源

- Awesome-Python
- Python Weekly

## 风格

1. 缩进：4个空格，无论在哪里
2. 每行最大长度：79
3. 空行：顶级函数与类定义之间两行，类内部函数定义间一行
4. 导入：

## 编码

...tbc

## 字符串

以我对计算机科学浅薄的的理解，计算机科学是一门处理字符串的科学，包括处理编码问题，所以掌握基本的字符串处理尤为重要。

Python 3中只有一种保存文本信息的数据类型，即 str （字符串 string ），字符串是不变的序列，保存的是 Unicode 码位。字节字符串用 bytes 对象来处理。

```Python
>>> list(b'Hello world')
[72, 101, 108, 108, 111, 32, 119, 111, 114, 108, 100]

>>> bytes([72, 101, 108, 108, 111, 32, 119, 111, 114, 108, 100])
b'Hello world'

>>> list('Hello world')
['H', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd']

# 编码与解码，默认参数是 ‘utf-8’
>>> 'Hello world'.encode()
b'Hello world'
>>> b'Hello world'.decode()
'Hello world'

>>> bytes('Hello world','utf-8')
b'Hello world'
```

字符串合并:

```Python
>>> ''.join(['H', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd'])
'Hello world'
>>> 'a' + 'b' + 'c'
'abc'
```

## 集合类型

list, tuple, dictionary, set, 4 种基本的集合类型，

### list vs tuple

list 是可变， 而 tuple 是不可变的， 一旦创建不可修改。

需要注意对 list 的各种操作的复杂度：Python 中的列表是由对**其他对象的引用**组成的的**连续数组**。指向这个数组的**指针及其长度**被保存在一个列表头结构中。Python 在创建这些数组时采用了指数过分配（exponential over-allocation）。

解释器在对列表推导进行求值的过程中并**不知道**最终结果容器的大小，也就无法为它预先分配数组的最终大小。因此，内部数组的重新分配方式与for循环中**完全相同**。但在许多情况下，与普通循环相比，使用列表推导创建列表要更加整洁、更加快速。

enumerate 枚举

```python
>>> for i, item in enumerate('Hello world'):
    print(i, item)


0 H
1 e
2 l
3 l
4 o
5  
6 w
7 o
8 r
9 l
10 d
```

zip 合并多个可迭代对象中的元素

```python
>>> for item in zip('hello',  'world'):
    print(item)


('h', 'w')
('e', 'o')
('l', 'r')
('l', 'l')
('o', 'd')
>>> for item in zip('hello w',  'world'):
    print(item)


('h', 'w')
('e', 'o')
('l', 'r')
('l', 'l')
('o', 'd')
```


## 迭代器

实现了迭代器协议的容器对象，

### 解压

星号表达式的变量永远是列表变量，如下 `*m`

```python
>>> data = [ 'ACME', 50, 91.1, (2012, 12, 21) ]
>>> f, *m, l = data
>>> f
'ACME'
>>> l
(2012, 12, 21)
>>> m
[50, 91.1]

```
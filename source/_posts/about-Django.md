---
title: About-Django
tags:
  - IT
  - Python
  - Django
  - Web-development
urlname: About-Django
date: 2020-04-21 22:47:15
---


从学习 Django 开始学习 Web 开发。

<!-- more -->

To do list

- [] 处理流程图
- [] url
- [] 视图
- [] 模型
- [] 模板
- [] 缓存
- [] 数据库
- [] 用户认证
- [] workflow
- [] 项目组织
- [] deploy
- [] 测试

## 视图 - view

### 函数视图 - FBV

### 类视图 - CBV

#### 资源

- 一个关于 [CBV](http://ccbv.co.uk/) 很赞的网站，网站里列出了 Django 提供的所有类视图，在单个类视图网页里列出了视图类的属性及方法以及它们的继承关系。

## 模型

每个模型被表示为 `django.db.models.Model` 类的子类，每个模型有许多类变量，它们都表示模型里的一个数据库字段（Field）。

### 字段类型

```python
AutoField # 做主键用，一般不需要直接使用
SmallAutoField # 1 to 32767
BigAutoField # 与上面的类似，1 to 9223372036854775807

IntegerField # 整数，-2147483648 to 2147483647
BigIntegerField # 与上面类似，-9223372036854775808 to 9223372036854775807，from 里是 textinput
SmallIntegerField # -32768 to 32767
PositiveIntegerField # 0 to 2147483647
PositiveSmallIntegerField # 0 to 32767
DecimalField # 十进制数，两个必须的参数，小数（decimal places）的位数和位数（必须大于小数的位数）
FloatField # 与上述类似，但是它对应的是 Python 中的 float

BooleanField # 真真假假
NullBooleanField # 要被放弃的字段，不要用

CharField # 字符串
TextField # 文本框
EmailField # 电子邮件地址
SlugField

DateField
DateTimeField
DurationField
TimeField

FileField
FilePathField
ImageField

GenericIPAddressField
URLField
UUIDField

ForeignKey
ManyToManyField
OneToOneField
```

## 数据库

### 数据库配置

以 PostgreSQL 为例，创建一个叫做 djdb 的数据库，进入数据库：

```shell
$ createdb djdb
$ psql djdb
```

创建用户 `djdbuser`，不设置密码

```sql
djdb=# CREATE USER djdbuser;
```

在 `settings.py` 中设置数据库如下：

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'djdb',
        'USER': 'djdbuser',
        'HOST': '127.0.0.1',
        'PORT': '5432',
    }
```

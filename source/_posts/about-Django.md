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

### 字段

#### 字段类型

```python
AutoField # 做主键用，一般不需要直接使用
SmallAutoField # 1 to 32767
BigAutoField # 与上面的类似，1 to 9223372036854775807
UUIDField # 通用唯一识别码

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

DateField # 日期，对应的是 Python 中的 datetime.date
DateTimeField # 对应的是 Python 中的 datetime.datetime
DurationField # 对应的是 Python 中的 datetime.timedelta，需要再实验下用法
TimeField # 对应的是 Python 中的 datetime.time

FileField # 文件上传字段，两个参数：upload_to（注意值可以是个函数）与 max_length（默认100），
FilePathField
ImageField # 继承自 FileField，可验证上传是否为有效图形。结合 Pillow。

GenericIPAddressField # IPv4 或者 IPv6 地址
URLField # 用于 URL 的CharField，默认长度是 200


ForeignKey
ManyToManyField
OneToOneField
```

#### 字段参数

一般参数，可选

```python
null # 默认 False，database-related，避免在字符串字段中使用，可以选用下一个 blank
blank # 默认 False，validation-related
choices # 两项的元组组成的迭代序列（如 list tuple），元组的第二项是第一项的可读名称，第二项也可以是个二项的元组序列，这样可以分组。
db_column # 指定字段在数据库中的列名，不设置则列名为字段名
db_index # 如果为 True，则将为此字段创建数据库索引。
db_tablespace # 
default # 
editable # 
error_messages # 
help_text # 
primary_key # 
unique # 
unique_for_date # 
unique_for_month # 
unique_for_year # 
verbose_name # 字段可读名称
validators # 
```

### Meta options

```python
abstract # 如果 abstract 是 True，那么这个模型将是一个抽象基类。
app_label # 
base_manager_name # 
db_table # 指定表名
Table names 表名 # 
db_tablespace # 
default_manager_name # 
default_related_name # 
get_latest_by # 
managed # 
order_with_respect_to # 
ordering # 
permissions # 
default_permissions # 
proxy # 
required_db_features # 
required_db_vendor # 
select_on_save # 
indexes # 
unique_together # 
index_together # 
constraints # 
verbose_name # 
verbose_name_plural # 
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
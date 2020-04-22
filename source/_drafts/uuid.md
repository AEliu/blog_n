---
title: 通用唯一识别码
tags:
---

## 是什么

通用唯一识别码是一个唯一的标识符，英语：Universally Unique Identifier，缩写：UUID，是用于计算机体系中以识别信息数目的一个128位标识符，具有分布性和唯一性的特点。根据标准方法生成，不依赖中央机构的注册和分配，UUID具有唯一性，重复UUID码概率接近零，可以忽略不计。具体看参看 [RFC 4122](https://www.ietf.org/rfc/rfc4122.txt)。

## 历史

## 如何产生

Python 中可以利用标准库的 UUID 产生，例如此刻：

```python
>>> import uuid
>>> uuid.uuid4() # Generate a random UUID
UUID('3f40d91f-3ae5-4e3b-bd16-0702225323ad')
```

## 有什么用

---
title: unorm 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
dev_langs:
- C++
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 131a928c5943ab9bf4dcc327b044d76e5646ede7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377378"
---
# <a name="unorm-class"></a>unorm 类

表示 unorm 数字。 每个元素是一个浮点数，范围内的 [0.0f，1.0f]。

## <a name="syntax"></a>语法

```
class unorm;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[unorm 构造函数](#ctor)|已重载。 默认构造函数。 初始化为 0.0f。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|unorm::operator--||
|unorm::operator float|转换运算符。 将 unorm 数字转换为浮点值。|
|unorm::operator*=||
|unorm::operator/=||
|unorm::operator++||
|unorm::operator+=||
|unorm::operator=||
|unorm::operator-=||

## <a name="inheritance-hierarchy"></a>继承层次结构

`unorm`

## <a name="requirements"></a>要求

**标头：** amp_short_vectors.h

**Namespace:** concurrency:: graphics

##  <a name="ctor"></a> unorm

默认构造函数。 初始化为 0.0f。

```
unorm(
    void) restrict(amp,
    cpu);

explicit unorm(
    float _V) restrict(amp,
    cpu);

explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

explicit unorm(
    int _V) restrict(amp,
    cpu);

explicit unorm(
    double _V) restrict(amp,
    cpu);

unorm(
    const unorm& _Other) restrict(amp,
    cpu);

inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>参数

*（_V)*<br/>
用来初始化的值。

*_Other*<br/>
用于初始化的标准对象。

## <a name="see-also"></a>请参阅

[Concurrency::graphics 命名空间](concurrency-graphics-namespace.md)

---
title: 'Platform:: arrayreference 类 |Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
dev_langs:
- C++
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d11aa58ba502e4e5eb4122e1d596da978a4e4ef6
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106557"
---
# <a name="platformarrayreference-class"></a>Platform::ArrayReference 类

`ArrayReference` 是在你希望用输入数据填充 C 样式数组时可以在输入参数中替换 [Platform::Array^](../cppcx/platform-array-class.md) 的优化类型。

## <a name="syntax"></a>语法

```cpp
class ArrayReference
```

### <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[Arrayreference:: Arrayreference](#ctor)|初始化 `ArrayReference` 类的新实例。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[ArrayReference::operator() 运算符](#operator-call)|将此 `ArrayReference` 转换为 `Platform::Array<T>^*`。|
|[ArrayReference::operator= 运算符](#operator-assign)|将另一 `ArrayReference` 的内容分配给此实例。|

## <a name="exceptions"></a>异常

### <a name="remarks"></a>备注

通过使用 `ArrayReference` 填充 C 样式数组，可避免在先复制到 `Platform::Array` 变量，然后复制到 C 样式数组时涉及额外的重复操作。 当你使用 `ArrayReference`时，只有一个复制操作。 有关代码示例，请参阅[Array 和 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)。

### <a name="requirements"></a>要求

**支持的最低客户端：** Windows 8

**支持的最低服务器：** Windows Server 2012

**命名空间：** Platform

**标头：** vccorlib.h

## <a name="ctor"></a>  Arrayreference:: Arrayreference 构造函数

初始化的新实例[platform:: arrayreference](../cppcx/platform-arrayreference-class.md)类。

### <a name="syntax"></a>语法

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)

```

### <a name="parameters"></a>参数

*dataArg*<br/>
指向数组数据的指针。

*sizeArg*<br/>
源数组中的元素数。

*otherArg*<br/>
其数据将移动以初始化新实例的 `ArrayReference` 对象。

### <a name="remarks"></a>备注

## <a name="operator-assign"></a>  Arrayreference:: Operator = 运算符

将指定的对象分配给当前[platform:: arrayreference](../cppcx/platform-arrayreference-class.md)通过使用移动语义的对象。

### <a name="syntax"></a>语法

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>参数

*otherArg*<br/>
移动到当前 `ArrayReference` 对象的对象。

### <a name="return-value"></a>返回值

对类型为 `ArrayReference` 的对象的引用。

### <a name="remarks"></a>备注

`Platform::ArrayReference` 是标准 C++ 类模板，而不是 ref 类。

## <a name="operator-call"></a>  ArrayReference::operator() 运算符

将当前[platform:: arrayreference](../cppcx/platform-arrayreference-class.md)对象返回到[platform:: array](../cppcx/platform-array-class.md)类。

### <a name="syntax"></a>语法

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>返回值

`Array<TArg>^` 类型的句柄到对象

### <a name="remarks"></a>备注

[Platform:: arrayreference](../cppcx/platform-arrayreference-class.md)并[platform:: array](../cppcx/platform-array-class.md)是标准 c + + 类模板，而不是 ref 类。

## <a name="see-also"></a>请参阅

[平台命名空间](../cppcx/platform-namespace-c-cx.md)
---
title: SRWLockExclusiveTraits 结构 |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7737c802634b618b9ea363c231a44d9381ad30ae
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235160"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 结构

描述的常见特征`SRWLock`中排他锁模式的类。

## <a name="syntax"></a>语法

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称   | 描述
------ | --------------------------------------------------------------------------
`Type` | 一个指向同义词[SRWLOCK](../windows/srwlock-class.md)类。

### <a name="public-methods"></a>公共方法

名称                                                        | 描述
----------------------------------------------------------- | --------------------------------------------------------------------
[Srwlockexclusivetraits:: Getinvalidvalue](#getinvalidvalue) | 检索`SRWLockExclusiveTraits`始终是无效的对象。
[Srwlockexclusivetraits:: Unlock](#unlock)                   | 释放指定的全权控制`SRWLock`对象。

## <a name="inheritance-hierarchy"></a>继承层次结构

`SRWLockExclusiveTraits`

## <a name="requirements"></a>要求

**标头：** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="getinvalidvalue"></a>Srwlockexclusivetraits:: Getinvalidvalue

检索`SRWLockExclusiveTraits`始终是无效的对象。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>返回值

一个空 `SRWLockExclusiveTraits` 对象。

## <a name="unlock"></a>Srwlockexclusivetraits:: Unlock

释放指定的全权控制`SRWLock`对象。

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>参数

*srwlock*<br/>
句柄`SRWLock`对象。

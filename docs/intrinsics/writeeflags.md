---
title: __writeeflags |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writeeflags
dev_langs:
- C++
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 875945c4116f99a0a7e8ef53666f432987ba0deb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424531"
---
# <a name="writeeflags"></a>__writeeflags

指定的值写入程序状态和控件 (EFLAGS) 注册。

## <a name="syntax"></a>语法

```
void __writeeflags(unsigned Value);
void __writeeflags(unsigned __int64 Value);
```

#### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*值*|[in]要写入到 EFLAGS 寄存器的值。 `Value`参数为 32 位长的 32 位平台和 64 位长的时间在 64 位平台。|

## <a name="remarks"></a>备注

这些例程只能用作内部函数可使用。

## <a name="requirements"></a>要求

|内部函数|体系结构|
|---------------|------------------|
|`__writeeflags`|x86、x64|

**标头文件** \<intrin.h >

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)<br/>
[__readeflags](../intrinsics/readeflags.md)
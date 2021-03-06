---
title: __vmx_vmread |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmread
dev_langs:
- C++
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d9483dafd763112f31f5299a5e0e7e54c224459
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821018"
---
# <a name="vmxvmread"></a>__vmx_vmread

**Microsoft 专用**

从当前的虚拟机控件结构 (VMCS) 读取指定的字段并将其放在指定的位置。

## <a name="syntax"></a>语法

```
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

#### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*字段*|[in]要读取的 VMCS 字段。|
|*FieldValue*|[in]指向要存储值的位置的读取由指定的 VMCS 字段`Field`参数。|

## <a name="return-value"></a>返回值

|“值”|含义|
|-----------|-------------|
|0|操作成功。|
|1|操作失败，当前 VMCS 的 `VM-instruction error field` 中提供了扩展状态。|
|2|操作失败，无可用状态。|

## <a name="remarks"></a>备注

`__vmx_vmread`函数等同于`VMREAD`计算机指令。 值`Field`参数是 Intel 文档中所述的编码的字段索引。 有关详细信息，搜索"Intel 虚拟化技术规范的 IA-32 Intel 体系结构，"文档在文档数字 C97063 002 [Intel Corporation](https://software.intel.com/articles/intel-sdm)站点，则请查阅该文档的附录 C.

## <a name="requirements"></a>要求

|内部函数|体系结构|
|---------------|------------------|
|`__vmx_vmread`|X64|

**标头文件** \<intrin.h >

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)
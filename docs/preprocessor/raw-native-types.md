---
title: raw_native_types |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_native_types
dev_langs:
- C++
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 067b109757f14e1b76c292bbae5a2ea7d688eae2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393616"
---
# <a name="rawnativetypes"></a>raw_native_types
**C + + 专用**  
  
禁止在高级包装器函数中使用 COM 支持类，并强制改用低级数据类型。      
  
## <a name="syntax"></a>语法  
  
```  
raw_native_types  
```  
  
## <a name="remarks"></a>备注  
 
默认情况下，高级错误处理方法使用 COM 支持类[_bstr_t](../cpp/bstr-t-class.md)并[_variant_t](../cpp/variant-t-class.md)来代替`BSTR`和`VARIANT`数据类型和原始 COM 接口指针。 这些类封装了为这些数据类型分配和解除分配内存存储的详细信息，并大大简化了类型强制转换和转换操作。  
  
**结束 c + + 专用**  
  
## <a name="see-also"></a>请参阅  
 
[#import 属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
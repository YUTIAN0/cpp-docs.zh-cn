---
title: no_smart_pointers |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_search_pointers
dev_langs:
- C++
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a01e6cf423aece9fba74c4b81fa247d57844e107
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439882"
---
# <a name="nosmartpointers"></a>no_smart_pointers
**C + + 专用**  
  
取消对类型库中所有接口的智能指针的创建。  
  
## <a name="syntax"></a>语法  
  
```  
no_smart_pointers  
```  
  
## <a name="remarks"></a>备注  
 
默认情况下，当使用 `#import` 时，您将获得针对类型库中的所有接口的智能指针声明。 这些智能指针都是类型[_com_ptr_t 类](../cpp/com-ptr-t-class.md)。  
  
**结束 c + + 专用**  
  
## <a name="see-also"></a>请参阅  
 
[#import 属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
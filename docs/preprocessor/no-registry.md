---
title: no_registry |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_registry
dev_langs:
- C++
helpviewer_keywords:
- no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8071fdf5e18542273dddfacecca913130e7bdea6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381226"
---
# <a name="noregistry"></a>no_registry
**no_registry**告知编译器不搜索的类型库导入注册表`#import`。  
  
## <a name="syntax"></a>语法  
  
```  
#import filename no_registry  
```  
  
### <a name="parameters"></a>参数  
*filename*  
类型库。  
  
## <a name="remarks"></a>备注  
 
如果在包含目录中找不到引用的类型库，编译将失败，即使在注册表中的类型库。  **no_registry**将传播到使用隐式导入其他类型库`auto_search`。  
  
编译器绝不会在寄存器中搜索由文件名指定并直接传递到 `#import` 的类型库。  
  
当`auto_search`指定，则其他`#import`s 将生成具有**no_registry**的初始设置`#import`(如果初始`#import`指令**no_registry**、 一个`auto_search`-生成`#import`也**no_registry**。)  
  
**no_registry**如果你想要导入跨引用的类型库，而无需在注册表中查找该文件的较旧版本的编译器的风险非常有用。 **no_registry**也是很有用，如果未注册类型库。  
  
## <a name="see-also"></a>请参阅  
 
[#import 属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
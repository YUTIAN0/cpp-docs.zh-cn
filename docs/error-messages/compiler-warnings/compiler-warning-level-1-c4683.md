---
title: 编译器警告 （等级 1） C4683 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4683
dev_langs:
- C++
helpviewer_keywords:
- C4683
ms.assetid: e6e77364-dba1-46dd-ae1d-03da23070bce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a157d3beb7c2efa7f1144a961973652e2ce384f7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194192"
---
# <a name="compiler-warning-level-1-c4683"></a>编译器警告（等级 1）C4683

> '*函数*： 事件源有输出的参数; 遇到警告时挂接多个事件处理程序

## <a name="remarks"></a>备注

如果多个事件接收器侦听 COM 事件源，可能会忽略输出参数的值。

请注意以下情况下会发生内存泄漏：

1. 如果方法具有输出参数在内部分配的例如 BSTR *。

2. 如果事件的多个处理程序 （是多路广播的事件）。

泄漏的原因是输出参数，将设置的多个处理程序，但只能由最后一个处理程序返回到调用站点。

## <a name="example"></a>示例

下面的示例生成 C4683 并演示如何修复此错误：

```cpp
// C4683.cpp
// compile with: /W1 /LD
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="xx") ];

[ object ]
__interface I {
   HRESULT f([out] int* pi);
   // try the following line instead
   // HRESULT f(int* pi);
};

[ coclass, event_source(com) ]
struct E {
   __event __interface I;   // C4683
};
```
---
title: 编译器警告 （等级 3） C4534 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4534
dev_langs:
- C++
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad85a6b9dff1715cbdce9738608f26c8680319d0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099806"
---
# <a name="compiler-warning-level-3-c4534"></a>编译器警告（等级 3）C4534

constructor 不会类 class 由于默认自变量的默认构造函数

非托管的类可以具有默认值的参数的构造函数，并且编译器将使用此为默认构造函数。 标记的类`value`关键字将不用作构造函数使用默认值对于其参数的默认构造函数。

有关详细信息，请参阅[类和结构](../../windows/classes-and-structs-cpp-component-extensions.md)。

下面的示例生成 C4534:

```
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```
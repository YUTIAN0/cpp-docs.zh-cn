---
title: 编译器错误 C3842 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3842
dev_langs:
- C++
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8db69ce3af28ed5878c43775b2c33542e5c817d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055516"
---
# <a name="compiler-error-c3842"></a>编译器错误 C3842

“函数”: 不支持在 WinRT 或托管类型的成员函数上使用“const”和“volatile”限定符

[const](../../cpp/const-cpp.md)并[易失性](../../cpp/volatile-cpp.md)不支持 Windows 运行时或托管的类型的成员函数上。

下面的示例生成 C3842：

```
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```
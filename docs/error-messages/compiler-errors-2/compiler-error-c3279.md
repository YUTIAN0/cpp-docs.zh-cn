---
title: 编译器错误 C3279 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3279
dev_langs:
- C++
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89c537da9bcf91e7774353cc1516a4c44e28649c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056763"
---
# <a name="compiler-error-c3279"></a>编译器错误 C3279

不允许对在 cli 命名空间中声明的类模板进行部分专用化、显式专用化和显式实例化

`cli` 命名空间由 Microsoft 定义并包含伪模板。 Visual C++ 编译器不允许对此命名空间中的类模板进行用户定义专用化、部分专用化、显式专用化和显式实例化。

以下示例生成 C3279：

```
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```
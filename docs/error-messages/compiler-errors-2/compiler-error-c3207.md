---
title: 编译器错误 C3207 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3207
dev_langs:
- C++
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d649e67fab3e1b3198d46db34233220a97076c7c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029749"
---
# <a name="compiler-error-c3207"></a>编译器错误 C3207

“function”：“arg”的模板参数无效，应当是类模板

将模板函数定义为采用模板模板参数。 但是，传递的是模板类型参数。

以下示例生成 C3207：

```
// C3207.cpp
template <template <class T> class TT>
void f(){}

template <class T>
struct S
{
};

void f1()
{
   f<S<int> >();   // C3207
   // try the following line instead
   // f<S>();
}
```
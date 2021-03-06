---
title: 编译器警告 （等级 1） C4091 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4091
dev_langs:
- C++
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b8fd377ed8b1f6425f0a1c13a83531fca1b797f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114093"
---
# <a name="compiler-warning-level-1-c4091"></a>编译器警告 （等级 1） C4091

keyword： 没有声明变量时忽略角的 type

编译器检测到用户可能预期的变量声明，但编译器无法声明变量的情况。

## <a name="example"></a>示例

一个`__declspec`用户定义类型声明的开始处的特性应用于该类型的变量。 C4091 指示没有声明变量。 下面的示例生成 C4091。

```
// C4091.cpp
// compile with: /W1 /c
__declspec(dllimport) class X {}; // C4091

// __declspec attribute applies to varX
__declspec(dllimport) class X2 {} varX;

// __declspec attribute after the class or struct keyword
// applies to user defined type
class __declspec(dllimport) X3 {};
```

## <a name="example"></a>示例

如果标识符是一个 typedef，它也不能为变量的名称。 下面的示例生成 C4091。

```
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```
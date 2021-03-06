---
title: 编译器错误 C2059 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2059
dev_langs:
- C++
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78640f61cb1d0f81fc405cbc3cfce16be0de5022
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890070"
---
# <a name="compiler-error-c2059"></a>编译器错误 C2059

语法错误: token

该标记导致语法错误。

下面的示例生成声明的行的错误消息`j`。

```
// C2059e.cpp
// compile with: /c
// C2143 expected
// Error caused by the incorrect use of '*'.
   int j*; // C2059
```

若要确定错误的原因，请检查错误消息中列出的行不仅上面的行。 如果对行的检查任何线索有关的问题，请尝试注释掉错误消息中列出的一行，并可能是上面的若干行。

如果符号紧随上会出现错误消息`typedef`变量，请确保，在源代码中定义的变量。

如果符号的计算结果执行任何操作，可能会出现，可能会收到 C2059 时 **/D** `symbol` **=** 用于编译。

```
// C2059a.cpp
// compile with: /DTEST=
#include <stdio.h>

int main() {
   #ifdef TEST
      printf_s("\nTEST defined %d", TEST);   // C2059
   #else
      printf_s("\nTEST not defined");
   #endif
}
```

编译函数的默认参数中指定了结构的应用程序时可能 C2059 的另一种情况。 参数的默认值必须是一个表达式。 初始值设定项列表 — 例如，一个用来初始化一个结构 — 不是表达式。  若要解决此问题，请定义一个构造函数来执行所需的初始化。

下面的示例生成 C2059:

```
// C2059b.cpp
// compile with: /c
struct ag_type {
   int a;
   float b;
   // Uncomment the following line to resolve.
   // ag_type(int aa, float bb) : a(aa), b(bb) {}
};

void func(ag_type arg = {5, 7.0});   // C2059
void func(ag_type arg = ag_type(5, 7.0));   // OK
```

C2059 可能格式不正确的强制转换。

下面的示例生成 C2059:

```
// C2059c.cpp
// compile with: /clr
using namespace System;
ref class From {};
ref class To : public From {};

int main() {
   From^ refbase = gcnew To();
   To^ refTo = safe_cast<To^>(From^);   // C2059
   To^ refTo2 = safe_cast<To^>(refbase);   // OK
}
```

如果您尝试创建命名空间名称包含句点，也可能发生 C2059。

下面的示例生成 C2059:

```
// C2059d.cpp
// compile with: /c
namespace A.B {}   // C2059

// OK
namespace A  {
   namespace B {}
}
```

会发生 C2059 时可限定名称的运算符 (`::`， `->`，并`.`) 关键字后面必须跟`template`，在此示例中所示：

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::Rebind<X>::Other AX; // error C2059
};

```

默认情况下，C++ 会假定 `AY::Rebind` 不是模板；因此，后面的 `<` 解释为小于号。  必须显式告知编译器 `Rebind` 是模板，以便其正确分析尖括号。 若要更正此错误，请在依赖类型的名称上使用 `template` 关键字，如下所示：

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::template Rebind<X>::Other AX; // correct
};

```
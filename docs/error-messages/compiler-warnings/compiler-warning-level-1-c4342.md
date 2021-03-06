---
title: 编译器警告 （等级 1） C4342 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4342
dev_langs:
- C++
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aeb582ff891cc9d186604af5d2ca2c2844b1cb0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016255"
---
# <a name="compiler-warning-level-1-c4342"></a>编译器警告（等级 1）C4342

行为更改: '*函数*调用，但在以前的版本中，称为成员运算符

在 Visual Studio 2002 之前的 Visual c + + 的版本中，调用了成员，但此行为已更改和编译器现在在命名空间范围内找到最佳匹配项。

如果找到一个成员运算符，编译器会以前不考虑任何命名空间范围运算符。 如果在命名空间范围更好地匹配，当前编译器正确调用它，而早期的编译器则不予以考虑。

您已成功将代码移植到最新版本后，应禁用此警告。  编译器可能会误报，生成此警告的代码没有任何行为更改。

默认情况下，此警告处于关闭状态。 有关详细信息，请参阅 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。

下面的示例生成 C4342:

```cpp
// C4342.cpp
// compile with: /EHsc /W1
#include <fstream>
#pragma warning(default: 4342)
using namespace std;
struct X : public ofstream {
   X();
};

X::X() {
   open( "ofs_bug_ev.txt." );
   if ( is_open() ) {
      *this << "Text" << "<-should be text" << endl;   // C4342
      *this << ' ' << "<-should be space symbol" << endl;   // C4342
   }
}

int main() {
   X b;
   b << "Text" << "<-should be text" << endl;
   b << ' ' << "<-should be space symbol" << endl;
}
```
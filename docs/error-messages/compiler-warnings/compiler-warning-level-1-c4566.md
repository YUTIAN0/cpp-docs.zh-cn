---
title: 编译器警告 （等级 1） C4566 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4566
dev_langs:
- C++
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c25ff9d2a4c915570a28752d11778983f2cf2fc3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049171"
---
# <a name="compiler-warning-level-1-c4566"></a>编译器警告（等级 1）C4566

表示通用字符名称 'char' 字符不能出现在当前代码页 （页）

不是每个 Unicode 字符可表示当前的 ANSI 代码页中。

窄字符串 （单字节字符） 转换为多字节字符，而不是宽字符串 （双字节字符）。

下面的示例生成 C4566:

```
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```
---
title: 编译器错误 C3363 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3363
dev_langs:
- C++
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe5ee58d5d11c2f3bad07b2a017a5ff83c6b0cb5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089122"
---
# <a name="compiler-error-c3363"></a>编译器错误 C3363

“type”：“typeid”只能应用于类型

[typeid](../../windows/typeid-cpp-component-extensions.md) 运算符未正确使用。

## <a name="example"></a>示例

下面的示例生成 C3363。

```
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```
---
title: 编译器错误 C3851 |Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6d0f6da9c3295aa6a8fad4bf5dfd8e725424739
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032465"
---
# <a name="compiler-error-c3851"></a>编译器错误 C3851

> '*char*： 通用字符名称不能指定基本字符集中的字符

## <a name="remarks"></a>备注

在编译为 C++ 的代码中，无法使用在字符串或字符文本之外表示基本源字符集中的字符的通用字符名称。 有关详细信息，请参阅[字符集](../../cpp/character-sets.md)。 在作为 C 编译的代码中，您不能使用字符的通用字符名称范围 0x20 0x7f，非独占，除了 0x24 （' $'） 中 0x40 ('\@)，或 0x60 ('\`)。

## <a name="example"></a>示例

下面的示例生成 C3851，并显示如何修复此问题：

```cpp
// C3851.cpp
int main()
{
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set
   int test2_A = 0;        // OK
}
```
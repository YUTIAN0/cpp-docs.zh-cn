---
title: 逻辑非运算符：! | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4594a8b1a881b6fa92909e7c7014087ff6240de8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211813"
---
# <a name="logical-negation-operator-"></a>逻辑非运算符：!

## <a name="syntax"></a>语法

```
! cast-expression
```

## <a name="remarks"></a>备注

逻辑求反运算符 (**！**) 反转其操作数的含义。 操作数必须是算法或指针类型（或计算结果为算法或指针类型的表达式）。 操作数将隐式转换为类型**bool**。 结果为 TRUE，如果转换后的操作数为 FALSE;如果转换后的操作数为 TRUE，则结果为 FALSE。 结果为类型**bool**。

表达式*e*，一元表达式`!e`等效于表达式`(e == 0)`，除涉及重载的运算符的。

## <a name="operator-keyword-for-"></a>! 的运算符关键字

**不**运算符是的备选的拼写 **！**。 有两种方法来访问**不**您的程序中的运算符： 包含头文件\<iso646.h >，或使用编译[/Za](../build/reference/za-ze-disable-language-extensions.md) （禁用语言扩展） 编译器选项。

## <a name="example"></a>示例

```cpp
// expre_Logical_NOT_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main() {
    int i = 0;
    if (!i)
        cout << "i is zero" << endl;
}
```

## <a name="see-also"></a>请参阅

[使用一元运算符的表达式](../cpp/expressions-with-unary-operators.md)<br/>
[C++ 内置运算符、优先级和关联性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[一元算术运算符](../c-language/unary-arithmetic-operators.md)<br/>

---
title: 成员访问运算符:。 和-&gt; |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- .
- ->
dev_langs:
- C++
helpviewer_keywords:
- member access, expressions
- operators [C++], member access
- dot operator (.)
- -> operator
- member access, operators
- postfix operators [C++]
- . operator
- member access
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c02183b3dc03c785ef5a6a08da80dd8435288b0a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112767"
---
# <a name="member-access-operators--and--gt"></a>成员访问运算符:。 和-&gt;

## <a name="syntax"></a>语法

```
postfix-expression . name
postfix-expression -> name
```

## <a name="remarks"></a>备注

成员访问运算符 **。** 并**->** 用于引用的结构、 联合和类成员。 成员访问表达式具有选定成员的值和类型。

有两种形式的成员访问表达式：

1. 在第一种形式，*后缀表达式*表示的结构、 类或联合类型值和*名称*命名指定的结构、 联合或类的成员。 操作的值为*名称*是左值，如果*后缀表达式*是左值。

1. 在第二个窗体*后缀表达式*表示指向结构、 联合或类的指针和*名称*命名指定的结构、 联合或类的成员。 值为*名称*和是左值。 **->** 运算符取消引用指针。 因此，表达式`e->member`并`(*e).member`(其中*e*表示的指针) 会产生相同的结果 (例外运算符**->** 或 <strong>\*</strong>重载)。

## <a name="example"></a>示例

以下示例演示成员访问运算符的两种形式。

```cpp
// expre_Selection_Operator.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

struct Date {
   Date(int i, int j, int k) : day(i), month(j), year(k){}
   int month;
   int day;
   int year;
};

int main() {
   Date mydate(1,1,1900);
   mydate.month = 2;
   cout  << mydate.month << "/" << mydate.day
         << "/" << mydate.year << endl;

   Date *mydate2 = new Date(1,1,2000);
   mydate2->month = 2;
   cout  << mydate2->month << "/" << mydate2->day
         << "/" << mydate2->year << endl;
   delete mydate2;
}
```

```Output
2/1/1900
2/1/2000
```

## <a name="see-also"></a>请参阅

[后缀表达式](../cpp/postfix-expressions.md)<br/>
[C++ 内置运算符、优先级和关联性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[类和结构](../cpp/classes-and-structs-cpp.md)<br/>
[结构和联合成员](../c-language/structure-and-union-members.md)
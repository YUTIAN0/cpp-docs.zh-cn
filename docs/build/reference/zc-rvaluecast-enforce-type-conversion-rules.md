---
title: '/Zc: rvaluecast （强制实施类型转换规则） |Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 626cabbec169d541a63dd65c22a7380718613b79
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706584"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast（强制实施类型转换规则）

当 **/zc: rvaluecast**指定选项，编译器正确将右值引用类型标识为根据 C + + 11 标准强制转换运算的结果。 未指定该选项时，编译器行为与 Visual Studio 2012 中的行为相同。

## <a name="syntax"></a>语法

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>备注

如果 **/zc: rvaluecast**指定，则编译器遵循 C + + 11 标准的 5.4 节，将仅强制转换表达式的转换导致对非函数类型的右值引用的表达式和导致非引用类型作为右值类型。 默认情况下，或者如果 **/Zc:rvalueCast-** 指定，编译器是不符合规范，并将所有导致右值引用视为右值的强制转换表达式。 为达到一致性并消除在使用转换中的错误，我们建议你使用 **/zc: rvaluecast**。

默认情况下 **/zc: rvaluecast**处于关闭状态 (**/Zc:rvalueCast-**)。 [触发-](permissive-standards-conformance.md)编译器选项隐式设置此选项，但它可以通过重写 **/Zc:rvalueCast-**。

使用 **/zc: rvaluecast**如果强制转换表达式作为参数传递给采用右值引用类型的函数。 默认行为会导致编译器错误[C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md)编译器错误地确定强制转换表达式的类型。 此示例中正确显示编译器错误代码何时 **/zc: rvaluecast**未指定：

```cpp
// Test of /Zc:rvalueCast
// compile by using:
// cl /c /Zc:rvalueCast- make_thing.cpp
// cl /c /Zc:rvalueCast make_thing.cpp

#include <utility>

template <typename T>
struct Thing {
   // Construct a Thing by using two rvalue reference parameters
   Thing(T&& t1, T&& t2)
      : thing1(t1), thing2(t2) {}

   T& thing1;
   T& thing2;
};

// Create a Thing, using move semantics if possible
template <typename T>
Thing<T> make_thing(T&& t1, T&& t2)
{
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));
}

struct Test1 {
   long a;
   long b;

   Thing<long> test() {
      // Use identity casts to create rvalues as arguments
      return make_thing(static_cast<long>(a), static_cast<long>(b));
   }
};
```

在适当情况下，默认编译器行为可能不会报告错误 C2102。 在此示例中，编译器不会不报告错误时，采用了由标识转换创建的 rvalue 的地址如果 **/zc: rvaluecast**未指定：

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

有关 Visual C++ 中一致性问题的详细信息，请参阅 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../../ide/working-with-project-properties.md)。

1. 选择**配置属性** > **C/c + +** > **命令行**属性页。

1. 修改**其他选项**属性以包含 **/zc: rvaluecast** ，然后选择**确定**。

## <a name="see-also"></a>请参阅

[/Zc（一致性）](../../build/reference/zc-conformance.md)<br/>

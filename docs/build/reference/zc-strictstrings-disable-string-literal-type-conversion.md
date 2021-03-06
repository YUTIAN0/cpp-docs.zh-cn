---
title: '/Zc: strictstrings （禁用字符串文本类型转换） |Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:strictStrings
- strictStrings
dev_langs:
- C++
helpviewer_keywords:
- /Zc:strictStrings
- -Zc compiler options (C++)
- strictStrings
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5055d7d1e7804512fa8f1a72bbdb27c483d6fdd3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "42581134"
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>/Zc:strictStrings（禁用字符串文本类型转换）

指定后，编译器要求通过使用字符串文本初始化的指针符合严格的 `const` 限定。

## <a name="syntax"></a>语法

> **/Zc:strictStrings**[**-**]

## <a name="remarks"></a>备注

如果 **/zc: strictstrings**指定，则编译器强制执行标准 c + +`const`字符串文字，作为类型的限定资格的数组`const char`或数组`const wchar_t`，取决于声明。 字符串文本不可变，并且尝试修改一个字符串文本的内容将导致在运行时出现访问冲突错误。 必须将字符串指针声明为 `const` 以通过使用字符串文本将其初始化，或使用显式 `const_cast` 以初始化非 `const` 指针。 默认情况下，或者如果 **/Zc:strictStrings-** 指定，则编译器不强制实施标准 c + +`const`通过使用字符串文本初始化的字符串指针的限定资格。

**/Zc: strictstrings**选项默认情况下处于关闭状态。 [触发-](permissive-standards-conformance.md)编译器选项隐式设置此选项，但它可以通过重写 **/Zc:strictStrings-**。

使用 **/zc: strictstrings**选项来阻止编译的代码不正确。 此示例显示一个简单声明错误如何在运行时导致崩溃：

```cpp
// strictStrings_off.cpp
// compile by using: cl /W4 strictStrings_off.cpp
int main() {
   wchar_t* str = L"hello";
   str[2] = L'a'; // run-time error: access violation
}
```

当 **/zc: strictstrings**已启用，相同的代码中报告了错误的声明`str`。

```cpp
// strictStrings_on.cpp
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp
int main() {
   wchar_t* str = L"hello"; // error: Conversion from string literal
   // loses const qualifier
   str[2] = L'a';
}
```

如果使用 `auto` 声明字符串指针，则编译器将为你创建正确的 `const` 指针类型声明。 尝试修改 `const` 指针的内容将由编译器报告为错误。

> [!NOTE]
> Visual Studio 2013 中的 c + + 标准库不支持 **/zc: strictstrings**编译器选项在调试生成。 如果看到多个[C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md)中生成的错误输出，这可能是原因。

有关 Visual C++ 中一致性问题的详细信息，请参阅 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../../ide/working-with-project-properties.md)。

1. 选择**配置属性** > **C/c + +** > **命令行**属性页。

1. 修改**其他选项**属性以包含 **/zc: strictstrings** ，然后选择**确定**。

## <a name="see-also"></a>请参阅

[/Zc（一致性）](../../build/reference/zc-conformance.md)<br/>

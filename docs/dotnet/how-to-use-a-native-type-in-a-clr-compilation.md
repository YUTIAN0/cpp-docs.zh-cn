---
title: 如何： 在-clr 编译中使用本机类型 |Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3e56c3617b6b2a8168e35867c09858dffa84cea9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448059"
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>如何：在 /clr 编译中使用本机类型

可以定义中的本机类型 **/clr**编译并且程序集内从该本机类型的任何使用都是有效。 但是，本机类型不会从引用的元数据。

每个程序集必须包含将使用每个本机类型的定义。

有关详细信息，请参阅 [/clr（公共语言运行时编译）](../build/reference/clr-common-language-runtime-compilation.md)。

## <a name="example"></a>示例

此示例创建一个组件，它定义，并使用本机类型。

```
// use_native_type_in_clr.cpp
// compile with: /clr /LD
public struct NativeClass {
   static int Test() { return 98; }
};

public ref struct ManagedClass {
   static int i = NativeClass::Test();
   void Test() {
      System::Console::WriteLine(i);
   }
};
```

## <a name="example"></a>示例

本示例定义使用该组件的客户端。 请注意，它是错误访问的本机类型，除非它在编译单位中定义。

```
// use_native_type_in_clr_2.cpp
// compile with: /clr
#using "use_native_type_in_clr.dll"
// Uncomment the following 3 lines to resolve.
// public struct NativeClass {
//    static int Test() { return 98; }
// };

int main() {
   ManagedClass x;
   x.Test();

   System::Console::WriteLine(NativeClass::Test());   // C2653
}
```

## <a name="see-also"></a>请参阅

[使用 C++ 互操作（隐式 PInvoke）](../dotnet/using-cpp-interop-implicit-pinvoke.md)
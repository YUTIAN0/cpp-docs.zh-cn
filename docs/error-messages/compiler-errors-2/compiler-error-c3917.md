---
title: 编译器错误 C3917 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3917
dev_langs:
- C++
helpviewer_keywords:
- C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c98141d07bbe7d1990434d2a46f116a266be1c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072688"
---
# <a name="compiler-error-c3917"></a>编译器错误 C3917

'*属性*： 已过时的构造声明样式

属性或事件定义中使用从 Visual Studio 2005 之前版本的语法。

有关详细信息，请参阅 [property](../../windows/property-cpp-component-extensions.md)。

## <a name="example"></a>示例

```cpp
// C3917.cpp
// compile with: /clr /c
public ref class  C {
private:
   int m_length;
public:
   C() {
      m_length = 0;
   }

   property int get_Length();   // C3917

   // The correct property definition:
   property int Length {
      int get() {
         return m_length;
      }

      void set( int i ) {
         m_length = i;
      }
   }
};
```
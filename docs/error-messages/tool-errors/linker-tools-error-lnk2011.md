---
title: 链接器工具错误 LNK2011 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2011
dev_langs:
- C++
helpviewer_keywords:
- LNK2011
ms.assetid: 04991ef5-49d5-46c7-8eee-a9d1d3fc541e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18562a21886508ff0766641f95ac2e15b76fd424
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095386"
---
# <a name="linker-tools-error-lnk2011"></a>链接器工具错误 LNK2011

预编译的对象中; 未链接映像可能无法运行

如果使用预编译标头，链接要求必须链接的所有对象文件使用预编译标头创建。 如果必须使用与其他源文件生成使用预编译标头的源文件，现在必须包括与预编译标头一起创建的对象文件。

例如，如果编译 stub.cpp 与其他源文件创建供使用的预编译标头的文件，必须与 STUB.obj 链接或将发生此错误。 在下面的命令行中，第一条用于创建预编译标头，COMMON.pch 和中使用 PROG1.cpp PROG2.cpp 在两个和第三行中。 文件仅包含 STUB.cpp`#include`行 (相同`#include`线如下所示 PROG1.cpp 和 PROG2.cpp) 和仅用于生成预编译标头。 中的最后一行 STUB.obj 必须链接中以避免 LNK2011。

```
cl /c /Yccommon.h stub.cpp
cl /c /Yucommon.h prog1.cpp
cl /c /Yucommon.h prog2.cpp
link /out:prog.exe stub.obj prog1.obj prog2.obj
```
---
title: -Yu （使用预编译标头文件） |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yu
dev_langs:
- C++
helpviewer_keywords:
- Yu compiler option [C++]
- /Yu compiler option [C++]
- -Yu compiler option [C++]
- PCH files, use existing
- .pch files, use existing
- precompiled header files, use existing
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0b2935c10b5d99f4fa97163310a3e2cba3006b3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707741"
---
# <a name="yu-use-precompiled-header-file"></a>/Yu（使用预编译标头文件）

指示编译器使用当前编译中的现有预编译标头 (.pch) 文件。

## <a name="syntax"></a>语法

```
/Yu[filename]
```

## <a name="arguments"></a>自变量

*filename*<br/>
包含在源代码文件中使用的标头文件的名称 **#include**预处理器指令。

## <a name="remarks"></a>备注

包含文件的名称必须是两个相同 **/Yc**选项创建预编译标头和任何后续 **/Yu** ，该值指示使用预编译标头的选项。

有关 **/Yc**，`filename`指定的点的预编译会停止; 编译器预编译所有代码，但是`filename`并将使用包含文件和扩展的基名称生成预编译标头为.pch。

.Pch 文件必须已创建使用 **/Yc**。

编译器将作为预编译的.h 文件之前出现的所有代码。 它将跳到只需更高版本 **#include**与.h 文件关联的指令使用.pch 文件中包含的代码并进行编译后的所有代码`filename`。

在命令行中，不允许有空格之间 **/Yu**和`filename`。

当指定 **/Yu**选项而无需文件名称，在源应用程序必须包含[#pragma hdrstop](../../preprocessor/hdrstop.md)指定预编译标头，.pch 文件的文件名的杂注。 在这种情况下，编译器将使用预编译标头 （.pch 文件） 由名为[/Fp （名称。Pch 文件）](../../build/reference/fp-name-dot-pch-file.md)。 编译器将跳过该杂注的位置，从指定的杂注，预编译标头文件还原的已编译的状态并进行编译杂注后面的代码。 如果 **#pragma hdrstop**未指定文件名，编译器将查找具有派生自的基名称的扩展名为.pch 的源文件的名称的文件。 此外可以使用 **/Fp**选项可以指定不同的.pch 文件。

如果指定 **/Yu**选项不包含文件名称，并不能指定**hdrstop**杂注，生成一个错误消息和编译不成功。

如果 **/Yc** `filename`并 **/Yu** `filename`选项出现在相同的命令行上，并且引用相同的文件名， **/Yc** `filename`采用优先顺序，最多预编译所有代码和包括的命名的文件。 此功能简化了生成文件的写入。

由于.pch 文件包含有关计算机环境的信息以及有关程序的内存地址信息，应仅使用创建它时所在的计算机上的 pch 文件。

预编译标头的详细信息，请参阅：

- [/Y（预编译标头）](../../build/reference/y-precompiled-headers.md)

- [创建预编译标头文件](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 指定[/Yc （创建预编译标头文件）](../../build/reference/yc-create-precompiled-header-file.md)在项目中的.cpp 文件。

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../../ide/working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 单击**预编译标头**属性页。

1. 修改**通过文件创建/使用 PCH**属性或**创建/使用预编译标头**属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参见<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A>和<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>。

## <a name="examples"></a>示例

如果以下代码：

```
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
...
```

使用命令行编译`CL /YuMYAPP.H PROG.CPP`，编译器不会处理这三个保存在预处理所有这三个文件 （以及它们可能包含任何文件） 中所花费的时间从而 include 语句，但 myapp.pch，使用预编译代码。

可以使用[/Fp （名称。Pch 文件）](../../build/reference/fp-name-dot-pch-file.md)选项与 **/Yu**选项以指定.pch 文件的名称，如果名称不同于对任一文件名称参数 **/Yc**或源文件，如下所示的基名称以下：

```
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP
```

此命令指定名为 MYPCH.pch 的预编译标头文件。 编译器使用其内容以还原的所有标头文件达 myapp.h 预编译的状态。 由编译器进行编译的代码在 MYAPP.h 之后**包括**语句。

## <a name="see-also"></a>请参阅

[编译器选项](../../build/reference/compiler-options.md)<br/>
[设置编译器选项](../../build/reference/setting-compiler-options.md)
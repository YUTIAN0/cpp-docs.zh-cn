---
title: -GX （启用异常处理） |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gx
dev_langs:
- C++
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 095db3db73f2be4012efe39f3b8cd8e645ad46c3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718313"
---
# <a name="gx-enable-exception-handling"></a>/GX（启用异常处理）

已否决。 启用同步异常处理使用函数假设使用声明`extern "C"`永远不会引发异常。

## <a name="syntax"></a>语法

```
/GX
```

## <a name="remarks"></a>备注

**/GX**已弃用。 使用等效[/EHsc](../../build/reference/eh-exception-handling-model.md)选项。 有关不推荐使用的编译器选项的列表，请参阅**已弃用并删除的编译器选项**主题中[按类别列出的编译器选项](../../build/reference/compiler-options-listed-by-category.md)。

默认情况下 **/EHsc**，则等效于 **/GX**，实际上是通过使用 Visual Studio 开发环境编译时。 使用命令行工具时，指定的异常处理。 此命令的等效 **/GX-**。

有关详细信息，请参阅[c + + 异常处理](../../cpp/cpp-exception-handling.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[使用项目属性](../../ide/working-with-project-properties.md)。

1. 在导航窗格中，选择**配置属性**， **C/c + +**，**命令行**。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[编译器选项](../../build/reference/compiler-options.md)<br/>
[设置编译器选项](../../build/reference/setting-compiler-options.md)<br/>
[/EH（异常处理模型）](../../build/reference/eh-exception-handling-model.md)
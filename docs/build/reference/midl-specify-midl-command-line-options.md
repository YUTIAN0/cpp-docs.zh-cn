---
title: -MIDL （指定 MIDL 命令行选项） |Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2fa03920f60d7da4730bc46b23605ccfa13f6d7
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860376"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL（指定 MIDL 命令行选项）

指定 MIDL 命令行选项的响应文件

## <a name="syntax"></a>语法

> **/MIDL:\@**<em>文件</em>

## <a name="arguments"></a>自变量

文件<br/>
包含文件的名称[MIDL 命令行选项](/windows/desktop/Midl/general-midl-command-line-syntax)。

## <a name="remarks"></a>备注

必须给定的 IDL 文件转换为 TLB 文件的所有选项*文件*;不能链接器的命令行上指定 MIDL 命令行选项。 如果未指定 /MIDL，MIDL 编译器将调用使用 IDL 文件名称和任何其他选项。

该文件应包含每行一个 MIDL 命令行选项。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[设置 Visual c + + 项目属性](../../ide/working-with-project-properties.md)。

1. 选择**配置属性** > **链接器** > **嵌入的 IDL**属性页。

1. 修改**MIDL 命令**属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>。

## <a name="see-also"></a>请参阅

[设置链接器选项](../../build/reference/setting-linker-options.md)<br/>
[链接器选项](../../build/reference/linker-options.md)<br/>
[/IDLOUT（命名 MIDL 输出文件）](../../build/reference/idlout-name-midl-output-files.md)<br/>
[/IGNOREIDL（不将属性处理到 MIDL 中）](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/TLBOUT（命名 .TLB 文件）](../../build/reference/tlbout-name-dot-tlb-file.md)<br/>
[生成特性化程序](../../windows/building-an-attributed-program.md)

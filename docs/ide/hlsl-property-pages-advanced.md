---
title: HLSL 属性页：高级 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.SuppressStartupBanner
- VC.Project.FXCompilerTool.TreatWarningAsError
dev_langs:
- C++
ms.assetid: a4f05aed-2c0e-4e7d-b7a4-bc2f228112c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa1a15f6542da165b615970591f384b875dd588b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444549"
---
# <a name="hlsl-property-pages-advanced"></a>HLSL 属性页：高级

若要配置 HLSL 编译器 (fxc.exe) 的以下属性，请使用其“高级”属性页。 有关如何访问 HLSL 文件夹中的“高级”属性页，请参阅[使用项目属性](../ide/working-with-project-properties.md)。

## <a name="uielement-list"></a>UIElement 列表

- **取消显示启动版权标志**

   若要取消显示启动版权标志和信息消息，则为“是(/nologo)”，否则为“否”。 默认情况下，该值为“是(/nologo)”。

- **将警告视为错误**

   若将所有编译器警告视为错误，则为“是(/WX)”；否则为“否”。

## <a name="see-also"></a>请参阅

[“HLSL”属性页](../ide/hlsl-property-pages.md)<br>
[HLSL 属性页：常规](../ide/hlsl-property-pages-general.md)<br>
[HLSL 属性页：输出文件](../ide/hlsl-property-pages-output-files.md)
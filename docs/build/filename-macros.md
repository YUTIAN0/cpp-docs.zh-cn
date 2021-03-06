---
title: 文件名宏 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc231dfb156460a2a0cc383b6d038a98c6e2015b
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894403"
---
# <a name="filename-macros"></a>文件名宏

文件名宏是预定义为依赖关系 （在磁盘上的不完整的文件名规范） 中指定的文件名。 这些宏不需要括在括号内时调用;指定仅以 $ 所示。

|宏|含义|
|-----------|-------------|
|**$\@**|当前所指定的当前目标的全名 （路径、 基名称、 扩展）。|
|**$$\@**|当前所指定的当前目标的全名 （路径、 基名称、 扩展）。 仅在作为依赖项中有效。|
|**$&#42;**|当前目标的路径和基名称中去掉文件扩展名。|
|**$&#42;&#42;**|当前目标的所有依赖项。|
|**$?**|更高版本的时间戳比当前的目标的所有依赖项。|
|**$<**|更高版本的时间戳比当前的目标的依赖文件。 仅在推理规则中的命令中有效。|

若要指定预定义的文件名宏的一部分，请追加宏修饰符，并将修改后的宏括在括号中。

|修饰符|生成的文件名部分|
|--------------|-----------------------------|
|**D**|驱动器和目录|
|**B**|基名称|
|**F**|基名称和扩展名|
|**R**|驱动器、 目录和基名称|

## <a name="see-also"></a>请参阅

[特殊 NMAKE 宏](../build/special-nmake-macros.md)

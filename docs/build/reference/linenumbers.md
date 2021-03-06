---
title: -LINENUMBERS |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /linenumbers
dev_langs:
- C++
helpviewer_keywords:
- LINENUMBERS dumpbin option
- line numbers
- -LINENUMBERS dumpbin option
- /LINENUMBERS dumpbin option
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9b969f51733d9eb4c45ac5609b42920765a7ad5
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704040"
---
# <a name="linenumbers"></a>/LINENUMBERS

```
/LINENUMBERS
```

## <a name="remarks"></a>备注

此选项显示 COFF 行号。 在对象文件中存在的行数，如果它使用编译的程序数据库 (/Zi) C7 兼容 (/ Z7)，或仅限行号 (/Zd)。 可执行文件或 DLL 包含 COFF 行号，如果它与生成调试信息链接 (/debug)。

仅[/HEADERS](../../build/reference/headers.md) DUMPBIN 选项仅适用于使用产生的文件[/GL](../../build/reference/gl-whole-program-optimization.md)编译器选项。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](../../build/reference/dumpbin-options.md)
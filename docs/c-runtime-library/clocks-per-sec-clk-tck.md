---
title: CLOCKS_PER_SEC、CLK_TCK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- CLOCKS_PER_SEC
- CLK_TCK
dev_langs:
- C++
helpviewer_keywords:
- CLOCKS_PER_SEC
- CLK_TCK constant
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3c7eac1db91abf7a84e424f7166402f346d3e4e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033571"
---
# <a name="clockspersec-clktck"></a>CLOCKS_PER_SEC、CLK_TCK

## <a name="syntax"></a>语法

```

#include <time.h>
```

## <a name="remarks"></a>备注

时间（以秒为单位）是由 `clock` 函数返回的值除以 `CLOCKS_PER_SEC` 所得的值。 `CLK_TCK` 是等效的，但被视为已过时。

## <a name="see-also"></a>请参阅

[clock](../c-runtime-library/reference/clock.md)<br/>
[全局常量](../c-runtime-library/global-constants.md)
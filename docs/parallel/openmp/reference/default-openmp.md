---
title: 默认值 (OpenMP) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- default
dev_langs:
- C++
helpviewer_keywords:
- default OpenMP clause
- defaults, OpenMP clause
ms.assetid: 96055106-a8f0-40b3-8319-e412b6e07bf8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ea32f473d96c8f48c6628d8f71212269bd6d345
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392603"
---
# <a name="default-openmp"></a>default (OpenMP)

并行区域中指定的未区分范围的变量的行为。

## <a name="syntax"></a>语法

```
default(shared | none)
```

## <a name="remarks"></a>备注

`shared`它实际上是如果`default`未指定子句，则意味着并行区域内的任何变量将被视为如同它指定与[共享](../../../parallel/openmp/reference/shared-openmp.md)子句。 `none` 意味着在作用域不是使用并行区域中使用的任何变量[私有](../../../parallel/openmp/reference/private-openmp.md)，[共享](../../../parallel/openmp/reference/shared-openmp.md)，[减少](../../../parallel/openmp/reference/reduction.md)， [firstprivate](../../../parallel/openmp/reference/firstprivate.md)，或[lastprivate](../../../parallel/openmp/reference/lastprivate.md)子句将导致编译器错误。

`default` 适用于以下指令：

- [parallel](../../../parallel/openmp/reference/parallel.md)

- [for](../../../parallel/openmp/reference/for-openmp.md)

- [部分](../../../parallel/openmp/reference/sections-openmp.md)

有关详细信息，请参阅[2.7.2.5 默认](../../../parallel/openmp/2-7-2-5-default.md)。

## <a name="example"></a>示例

请参阅[私有](../../../parallel/openmp/reference/private-openmp.md)有关的使用示例`default`。

## <a name="see-also"></a>请参阅

[子句](../../../parallel/openmp/reference/openmp-clauses.md)
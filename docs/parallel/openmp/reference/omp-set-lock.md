---
title: omp_set_lock |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_lock OpenMP function
ms.assetid: ded839cb-ca19-403f-8622-eb52ce512d31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59a7bcc24b67e916271748740dd88568979d5a70
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401597"
---
# <a name="ompsetlock"></a>omp_set_lock

块线程执行，直到锁可用。

## <a name="syntax"></a>语法

```
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>参数

*lock*<br/>
类型的变量[omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md)与初始化[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)。

## <a name="remarks"></a>备注

有关详细信息，请参阅[3.2.3 omp_set_lock 和 omp_set_nest_lock 函数](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)。

## <a name="examples"></a>示例

请参阅[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)有关的使用示例`omp_set_lock`。

## <a name="see-also"></a>请参阅

[函数](../../../parallel/openmp/reference/openmp-functions.md)
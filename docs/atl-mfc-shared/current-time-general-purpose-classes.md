---
title: 当前时间： 通用类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- time, setting current
- current time, CTime object
- procedures, getting current time
- initializing objects, with the current time
- time, getting current
ms.assetid: c39e6775-6a92-4b27-95a7-5c86ed371d8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9edf381864121d4e3f6c5a2b6cf7c01198368e1e
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860519"
---
# <a name="current-time-general-purpose-classes"></a>当前时间： 通用类

下面的过程演示如何创建`CTime`对象并将其初始化与当前时间。

### <a name="to-get-the-current-time"></a>若要获取当前时间

1. 分配`CTime`对象时，按如下所示：

   [!code-cpp[NVC_ATLMFC_Utilities#171](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_1.cpp)]

   > [!NOTE]
   > 未初始化`CTime`对象未初始化为有效的时间。

1. 调用`CTime::GetCurrentTime`函数从操作系统获取当前时间。 此函数将返回`CTime`可以用于设置的值的对象`CTime`，按如下所示：

   [!code-cpp[NVC_ATLMFC_Utilities#172](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_2.cpp)]

   由于`GetCurrentTime`是从静态成员函数`CTime`类，必须限定其名称与类和范围解析运算符的名称 (`::`)， `CTime::GetCurrentTime()`。

当然，所述的两个步骤之前可以合并成单个程序语句，如下所示：

[!code-cpp[NVC_ATLMFC_Utilities#173](../atl-mfc-shared/codesnippet/cpp/current-time-general-purpose-classes_3.cpp)]

---
title: 删除未分配的符号 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], deleting
- symbols [C++], unassigned
- unassigned symbols
ms.assetid: 47641c46-1bad-44fb-8f85-79ae36919f13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c8ee38503698f6f4553ced630e996f58c76e08c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436541"
---
# <a name="deleting-unassigned-symbols"></a>删除未分配的符号

### <a name="to-delete-an-unassigned-unused-symbol"></a>删除未分配（未使用）的符号

1. 在中[资源符号对话框](../windows/resource-symbols-dialog-box.md)，选择你想要删除，并单击符号**删除**。

   > [!NOTE]
   > 在资源文件中删除未使用的符号之前，请确保它未在程序中的其他位置使用，也未由编译时包含的资源文件使用。

## <a name="requirements"></a>要求

Win32

## <a name="see-also"></a>请参阅

[更改未分配的符号](../windows/changing-unassigned-symbols.md)<br/>
[符号名限制](../windows/symbol-name-restrictions.md)<br/>
[符号值限制](../windows/symbol-value-restrictions.md)<br/>
[预定义的符号 ID](../windows/predefined-symbol-ids.md)
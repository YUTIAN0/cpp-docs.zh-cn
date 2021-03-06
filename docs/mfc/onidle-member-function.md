---
title: OnIdle 成员函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b334a4561af40b69bc367ab5b1129afa8fb29ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377288"
---
# <a name="onidle-member-function"></a>OnIdle 成员函数

正在处理任何 Windows 消息，框架将调用[CWinApp](../mfc/reference/cwinapp-class.md)成员函数[OnIdle](../mfc/reference/cwinapp-class.md#onidle) （MFC 库参考中所述）。

重写 `OnIdle` 以执行后台任务。 默认版本更新用户界面对象的状态（如工具栏按钮）并执行框架在其操作过程中创建的临时对象的清除。 下图演示消息循环如何在队列中没有消息时调用 `OnIdle`。

![消息循环过程](../mfc/media/vc387c1.gif "vc387c1")消息循环

可以在空闲循环中执行的操作的详细信息，请参阅[空闲循环处理](../mfc/idle-loop-processing.md)。

## <a name="see-also"></a>请参阅

[CWinApp：应用程序类](../mfc/cwinapp-the-application-class.md)

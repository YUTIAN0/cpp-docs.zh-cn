---
title: 使用 CSliderCtrl |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CSliderCtrl
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls [MFC], using
ms.assetid: 242c7bcd-126e-4b9b-8f76-8082ad06fe73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8dec5e0500d7857c8b6781cfd0f78fb18cf93349
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380305"
---
# <a name="using-csliderctrl"></a>使用 CSliderCtrl

[CSliderCtrl](../mfc/reference/csliderctrl-class.md)类表示滑块控件，这也称为跟踪条控件。 “滑块控件”是一个包含滑块和可选刻度线的窗口。 当用户使用鼠标或箭头键移动滑块时，滑块控件将发送通知消息来指示更改。

当您希望用户选择一个离散值或位于一个范围中的一组连续值时，滑动控件很有用。 例如，您可能使用滑块控件允许用户通过将滑块移动到给定刻度线来设置重复速率。

滑块控件中的滑块将按您在创建它时指定的增量移动。 例如，如果您指定滑块控件的范围应为 5，则滑块只能占用 6 个位置：滑块控件的左侧有一个位置，范围中每个增量各有一个位置。 通常，这些位置中的每个位置将用一个刻度线标识。

## <a name="what-do-you-want-to-know-more-about"></a>你想要了解更多信息

- [使用滑块控件](../mfc/using-slider-controls.md)

- [滑块控件样式](../mfc/slider-control-styles.md)

- [滑块控件成员函数](../mfc/slider-control-member-functions.md)

- [滑块通知消息](../mfc/slider-notification-messages.md)

## <a name="see-also"></a>请参阅

[控件](../mfc/controls-mfc.md)


---
title: 框架窗口类创建的应用程序向导 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CMainFrame
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], frame window classes created by
- window classes [MFC]
- classes [MFC], frame-window
- CMDIFrameWnd class [MFC], frame windows
- window classes [MFC], frame
- CFrameWnd class [MFC], frame windows
- CMDIChildWnd class [MFC], frame windows
- frame window classes [MFC], created by application wizards
- CMainFrame class [MFC]
ms.assetid: 9947df73-4470-49a0-ac61-7b6ee401a74e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aff98636c723de17056f4bef337b46f4a686ddec
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420603"
---
# <a name="frame-window-classes-created-by-the-application-wizard"></a>应用程序向导创建的框架窗口类

当你使用[应用程序向导](../ide/creating-desktop-projects-by-using-application-wizards.md)创建主干应用程序，除了应用程序、 文档和视图类，应用程序向导创建应用程序的主框架窗口的派生的框架窗口类。 默认情况下，此类名为 `CMainFrame`，包含此类的文件名为 MAINFRM.H 和 MAINFRM.CPP。

如果你的应用程序是 SDI，你`CMainFrame`类派生自类[CFrameWnd](../mfc/reference/cframewnd-class.md)。

如果应用程序是 MDI，`CMainFrame`派生自类[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)。 在此情况下，`CMainFrame` 实现保留菜单、工具栏和状态栏的主框架。 应用程序向导不会为您派生新的文档框架窗口类。 相反，它使用中的默认实现[CMDIChildWnd 类](../mfc/reference/cmdichildwnd-class.md)。 MFC 框架会创建一个子窗口以包含应用程序要求的每个视图（可以是 `CScrollView`、`CEditView`、`CTreeView`、`CListView` 等类型）。 如果需要自定义文档框架窗口，可以创建新的文档框架窗口类 (请参阅[添加类](../ide/adding-a-class-visual-cpp.md))。

如果您选择支持工具栏，此类还具有类型的成员变量[CToolBar](../mfc/reference/ctoolbar-class.md)并[CStatusBar](../mfc/reference/cstatusbar-class.md)和一个`OnCreate`消息处理程序函数来初始化两个[控件条](../mfc/control-bars.md)。

这些框架窗口类在创建之后便可以工作，但要增强其功能，您必须添加成员变量和成员函数。 您可能还需要让您的窗口类处理其他 Windows 消息。 有关详细信息，请参阅[更改 MFC 创建的窗口样式](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)。

## <a name="see-also"></a>请参阅

[框架窗口类](../mfc/frame-window-classes.md)<br/>
[MFC 程序或控件的源文件和头文件](../ide/mfc-program-or-control-source-and-header-files.md)


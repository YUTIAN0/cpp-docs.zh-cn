---
title: “添加类”对话框 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.addclass
dev_langs:
- C++
helpviewer_keywords:
- Add Class dialog box
ms.assetid: 916259b8-8e5f-4267-bd10-313483beba67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1eb848ae20ba9a587bfdf14881e1a3df3bbeb31
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420278"
---
# <a name="add-class-dialog-box"></a>“添加类”对话框

“添加类”  对话框包含的模板允许你：

- 打开相应的代码向导（如果有可用的向导）。 有关详细信息，请参阅[用代码向导添加功能](../ide/adding-functionality-with-code-wizards-cpp.md)。

   \- 或 -

- 通过向项目中添加相应的文件和源代码，自动创建新类。

可以从“项目”菜单、“解决方案资源管理器”或[类视图](/visualstudio/ide/viewing-the-structure-of-code)访问“添加类”对话框。

> [!NOTE]
>  如果尝试将不适合的类添加到当前项目，则会收到错误信息。 单击“确定”  返回到“添加类”  对话框。

## <a name="add-class-templates"></a>添加类模板

有四种类别的“添加类”  模板：.NET、ATL、MFC 和泛型。 当在“模板”  窗格中选择模板时，描述所选内容的文本将出现在“类别”  和“模板”  窗格之下。

### <a name="net"></a>.NET

|模板|向导|
|--------------|------------|
|ASP.NET Web 服务|不可用|
|组件类 (.NET)|不可用|
|安装程序类 (.NET)|不可用|
|用户控件 (.NET)|不可用|
|Windows 窗体 (.NET)|不可用|

### <a name="atl"></a>ATL

|模板|向导|
|--------------|------------|
|向 MFC 添加 ATL 支持|不可用|
|ATL Active Server Page 组件|[ATL Active Server Page 组件向导](../atl/reference/atl-active-server-page-component-wizard.md)|
|ATL 控件|[ATL 控件向导](../atl/reference/atl-control-wizard.md)|
|ATL 对话框|[ATL 对话框向导](../atl/reference/atl-dialog-wizard.md)|
|ATL COM+ 1.0 组件|[ATL COM+ 1.0 组件向导](../atl/reference/atl-com-plus-1-0-component-wizard.md)|
|ATL OLEDB 使用者|[ATL OLE DB 使用者向导](../atl/reference/atl-ole-db-consumer-wizard.md)|
|ATL OLEDB 提供程序|[ATL OLE DB 提供程序向导](../atl/reference/atl-ole-db-provider-wizard.md)|
|ATL 属性页|[ATL 属性页向导](../atl/reference/atl-property-page-wizard.md)|
|ATL 简单对象|[ATL 简单对象向导](../atl/reference/atl-simple-object-wizard.md)|
|WMI 事件提供程序|WMI 事件提供程序向导|
|WMI 实例提供程序|WMI 实例提供程序向导|

### <a name="mfc"></a>MFC

|模板|向导|
|--------------|------------|
|MFC 类|[MFC 添加类向导](../mfc/reference/mfc-add-class-wizard.md)|
|ActiveX 控件中的 MFC 类|[从 ActiveX 控件添加类向导](../ide/add-class-from-activex-control-wizard.md)|
|TypeLib 中的 MFC 类|[从类型库添加类向导](../mfc/reference/add-class-from-typelib-wizard.md)|
|MFC ODBC 使用者|[MFC ODBC 使用者向导](../mfc/reference/mfc-odbc-consumer-wizard.md)|

### <a name="generic-classes"></a>泛型类

|模板|向导|
|--------------|------------|
|泛型 C++ 类|[一般 C++ 类向导](../ide/generic-cpp-class-wizard.md)|

## <a name="see-also"></a>请参阅

[添加成员函数](../ide/adding-a-member-function-visual-cpp.md)<br>
[添加成员变量](../ide/adding-a-member-variable-visual-cpp.md)<br>
[重写虚函数](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[MFC 消息处理程序](../mfc/reference/adding-an-mfc-message-handler.md)<br>
[导航类结构](../ide/navigating-the-class-structure-visual-cpp.md)
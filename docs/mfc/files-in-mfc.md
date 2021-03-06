---
title: MFC 中的文件 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serialization [MFC], MFC files
- I/O [MFC], MFC classes
- files [MFC], MFC
- files [MFC], serialization
- binary access, binary file operations in MFC
- file I/O classes [MFC]
- I/O [MFC]
- persistence [MFC]
- MFC, file operations
- files [MFC], manipulating
- binary access [MFC]
ms.assetid: ae25e2c5-2859-4679-ab97-438824e93ce1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bfc36a6b1610df07201833ed13a1c6ebd0ae6f7b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444472"
---
# <a name="files-in-mfc"></a>MFC 中的文件

在 Microsoft 基础类库 (MFC)，类[CFile](../mfc/reference/cfile-class.md)处理常规文件 I/O 操作。 此系列文章介绍如何打开和关闭文件以及如何读取数据并将数据写入文件。 还讨论了文件状态操作。 有关如何读取和写入数据文件中的一个替代方法使用 MFC 的基于对象的序列化功能的说明，请参阅文章[序列化](../mfc/serialization-in-mfc.md)。

> [!NOTE]
>  当你使用 MFC`CDocument`对象，该框架为您完成大部分的序列化工作。 具体而言，框架将创建和使用 `CFile` 对象。 只需编写代码中的重写`Serialize`类的成员函数`CDocument`。

`CFile` 类为通用二进制文件操作提供了一个接口。 派生自 `CStdioFile` 的 `CMemFile` 和 `CFile` 类以及派生自 `CSharedFile` 的 `CMemFile` 类提供了更专业的文件服务。

有关 MFC 文件处理的替代方法的详细信息，请参阅[文件处理](../c-runtime-library/file-handling.md)中*运行时库参考*。

有关信息派生`CFile`类，请参阅[MFC 层次结构图表](../mfc/hierarchy-chart.md)。

## <a name="what-do-you-want-to-do"></a>你想要做什么

*使用 CFile*

- [使用 CFile 打开文件](../mfc/opening-files.md)

- [读取和写入 CFile 的文件](../mfc/reading-and-writing-files.md)

- [关闭使用 CFile 文件](../mfc/closing-files.md)

- [使用 CFile 访问文件状态](../mfc/accessing-file-status.md)

*使用 MFC 序列化 （对象持久性）*

- [创建一个可序列化类](../mfc/serialization-making-a-serializable-class.md)

- [通过 CArchive 对象将对象序列化](../mfc/serialization-serializing-an-object.md)

- [创建 CArchive 对象](../mfc/two-ways-to-create-a-carchive-object.md)

- [使用 CArchive <\<和 >> 运算符](../mfc/using-the-carchive-output-and-input-operators.md)

- [存储和加载 Cobject 和 CObject 派生对象通过存档](../mfc/storing-and-loading-cobjects-via-an-archive.md)

## <a name="see-also"></a>请参阅

[概念](../mfc/mfc-concepts.md)<br/>
[常规 MFC 主题](../mfc/general-mfc-topics.md)<br/>
[CArchive 类](../mfc/reference/carchive-class.md)<br/>
[CObject 类](../mfc/reference/cobject-class.md)

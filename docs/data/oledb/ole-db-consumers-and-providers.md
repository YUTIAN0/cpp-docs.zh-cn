---
title: OLE DB 使用者和提供程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b37a06ec89f0e2e21c4332a480e58c605f0d161f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110713"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB 使用者和提供程序

OLE DB 体系结构使用使用者和提供程序的模型。 使用者发出数据请求。 一个提供程序通过将数据放在表格格式并将其返回给使用者响应这些请求。 必须在提供程序中实现使用者可以进行任何调用。  
  
定义从技术上讲，使用者是指任何通过 OLE DB 接口访问数据的系统或应用程序代码 （不一定是 OLE DB 组件）。 在提供程序中实现接口。 因此，一个提供程序是实现 OLE DB 接口来封装对数据的访问，并将其公开给其他对象 （即消费者） 的任何软件组件。  
  
根据角色，使用者调用的方法上 OLE DB 接口;OLE DB 访问接口实现所需的 OLE DB 接口。  
  
OLE DB 避免条款客户端和服务器，因为这些角色并不始终意义，尤其是在 n 层的情况下。 因为使用者可以是上一层中提供另一个组件的组件，才能调用此客户端组件会引起混乱。 此外，提供程序有时更像一个服务器的数据库驱动程序。  
  
## <a name="see-also"></a>请参阅  

[OLE DB 编程](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB 编程概述](../../data/oledb/ole-db-programming-overview.md)
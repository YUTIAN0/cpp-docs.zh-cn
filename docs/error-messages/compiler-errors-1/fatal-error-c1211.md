---
title: 错误 C1211 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1211
dev_langs:
- C++
helpviewer_keywords:
- C1211
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 444d2bc25c2eddd5ea9a0170272bd3e71b61f94f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018518"
---
# <a name="fatal-error-c1211"></a>错误 C1211

安装的运行时版本不支持 TypeForwardedTo 自定义特性

使用的编译器是当前版本而公共语言运行时是早期版本时将发生 C1211。

编译器的一些功能在早期的运行时版本中可能无效。

若要解决 C1211，请安装随当前所使用编译器一起提供的公共语言运行时。

有关详细信息，请参阅[类型转发 (C + + CLI)](../../windows/type-forwarding-cpp-cli.md)。
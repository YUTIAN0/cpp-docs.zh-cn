---
title: 编译器警告 （等级 1） C4711 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4711
dev_langs:
- C++
helpviewer_keywords:
- C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d184d5043dad1138f774ca7288a773bcc38c6d9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069934"
---
# <a name="compiler-warning-level-1-c4711"></a>编译器警告（等级 1）C4711

为内联展开选定了函数“function”

编译器在上执行给定的函数，尽管它没有标记为内联。

如果启用 C4711 [/ob2](../../build/reference/ob-inline-function-expansion.md)指定。

在由编译器自行执行内联。 此警告为信息性。

默认情况下，此警告处于关闭状态。 若要启用警告，请使用[#pragma 警告](../../preprocessor/warning.md)。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。
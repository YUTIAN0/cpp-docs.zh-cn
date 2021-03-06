---
title: 编译器限制 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76b08ab88ce5487485c8b8872488c0cf784ad2c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093540"
---
# <a name="compiler-limits"></a>编译器限制

C++ 标准建议对各种语言构造施加限制。 下面是 Visual C++ 编译器不会在其中实施建议的限制的情况的列表。 第一个数字是 ISO C++ 11 标准（INCITS/ISO/IEC 14882-2011[2012]，附件 B）中建立的限制，而第二个数字是由 Visual C++ 实现的限制：

- 嵌套级别的复合语句、 迭代控制结构和选择控制结构的 C++ 标准： 256，Visual C++ 编译器： 依赖于的语句嵌套的但通常介于 100 和 110 之间的组合。 

- 一个宏定义的 C++ 标准中的参数： 256，Visual C++ 编译器： 127。 

- 自变量在一个宏调用的 C++ 标准： 256，Visual C++ 编译器： 127。 

- 中的字符字符串文本或宽字符串文本 （串联后） 的 c + + 标准： 65536，Visual c + + 编译器： 65535 的单字节字符，包括 NULL 终止符，并包括 NULL 终止符的 32767 双字节字符。

- 单个 `struct-declaration-list` 中的嵌套类、结构或联合定义的级别 [C++ 标准：256]（Visual C++ 编译器：16）。

- 成员初始值设定项中的构造函数定义的 C++ 标准： 6144，Visual C++ 编译器： 至少为 6144。 

- 范围限定一个标识符的 C++ 标准： 256，Visual C++ 编译器： 127。 

- 嵌套**extern**规范的 c + + 标准： 1024，Visual c + + 编译器： 9 (不包括的隐式**extern**规范在全局作用域或 10，如果您要计算的隐式**extern**全局作用域中的规范...

- 模板声明的 C++ 标准中的模板自变量： 1024，Visual C++ 编译器： 2046年。

## <a name="see-also"></a>请参阅

[非标准行为](../cpp/nonstandard-behavior.md)
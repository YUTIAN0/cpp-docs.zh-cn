---
title: 链接器工具错误 LNK1179 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1179
dev_langs:
- C++
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d22ebb329d390d44aea44ff9dc6f3bf2f86a1d26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117447"
---
# <a name="linker-tools-error-lnk1179"></a>链接器工具错误 LNK1179

无效或损坏的文件： 重复的 COMDAT filename

对象模块包含两个或多个具有相同名称的 Comdat。

使用可导致此错误[/H](../../build/reference/h-restrict-length-of-external-names.md)，这就限制了外部名称的长度并[/Gy](../../build/reference/gy-enable-function-level-linking.md)，哪些程序包中排列的 Comdat 函数。

## <a name="example"></a>示例

在下面的代码中，`function1`和`function2`的前八个字符相同。 使用编译 **/Gy**并 **/H8**产生链接错误。

```
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```
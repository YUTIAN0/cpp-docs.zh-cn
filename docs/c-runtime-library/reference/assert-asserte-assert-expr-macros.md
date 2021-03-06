---
title: _ASSERT、_ASSERTE、_ASSERT_EXPR 宏 | Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _ASSERTE
- ASSERTE
- _ASSERT
- _ASSERT_EXPR
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 254550acf94acb846826bc0efe76ef26753c54b8
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107583"
---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT、_ASSERTE、_ASSERT_EXPR 宏

计算表达式，并在结果为时生成调试报告**False** （仅限调试版本）。

## <a name="syntax"></a>语法

```C
// Typical usage:
_ASSERT_EXPR( booleanExpression, message );
_ASSERT( booleanExpression );
_ASSERTE( booleanExpression );
```

### <a name="parameters"></a>参数

*布尔表达式*<br/>
计算结果不为零 (true) 或为零 (false) 的标量表达式（包括指针表达式）。

*message*<br/>
要显示为报告一部分的宽字符串。

## <a name="remarks"></a>备注

**_ASSERT_EXPR**， **_ASSERT**并 **_ASSERTE**宏提供简洁明了的机制，用于在调试过程中检查假设提供一个应用程序。 它们非常灵活，因为无需包含在 `#ifdef` 语句中，可防止在零售版本的应用程序中调用它们。 这种灵活性使用 [_DEBUG](../../c-runtime-library/debug.md) 宏来实现。 **_ASSERT_EXPR**， **_ASSERT**并 **_ASSERTE**时，才可 **_DEBUG**在编译时定义。 当 **_DEBUG**是未定义，对这些宏调用删除在预处理期间。

**_ASSERT_EXPR**， **_ASSERT**并 **_ASSERTE**评估其*布尔表达式*参数，则结果为**false**(0)，它们会打印诊断消息并调用[_CrtDbgReportW](crtdbgreport-crtdbgreportw.md)生成调试报告。 **_ASSERT**宏会打印简单的诊断消息， **_ASSERTE**在消息中，包括失败的表达式的字符串表示形式并 **_ASSERT_EXPR**包括*消息*诊断消息中的字符串。 这些宏不执行任何操作时*布尔表达式*的计算结果为非零值。

**_ASSERT_EXPR**， **_ASSERT**并 **_ASSERTE**调用 **_CrtDbgReportW**，这会使所有输出都采用宽字符。 **_ASSERTE**中正确打印 Unicode 字符*布尔表达式*并 **_ASSERT_EXPR**中打印 Unicode 字符*消息*。

因为 **_ASSERTE**宏会指定失败的表达式，并 **_ASSERT_EXPR**允许在生成的报告指定一条消息，它们使用户能够确定此问题，而不引用应用程序源代码。 但是，缺点中存在的每个*消息*打印 **_ASSERT_EXPR**并评估每个表达式 **_ASSERTE**包括在输出 （调试版本）应用程序作为一个字符串常量的文件。 因此，如果大量的在调用 **_ASSERT_EXPR**或 **_ASSERTE**，这些表达式可以极大地增加输出文件的大小。

除非使用 [_CrtSetReportMode](crtsetreportmode.md) 和 [_CrtSetReportFile](crtsetreportfile.md) 函数另行指定，否则消息会出现在弹出对话框中，这等于设置以下内容：

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_CrtDbgReportW**生成调试报告并确定其目标或目标，基于为定义文件或当前报告模式和模式 **_CRT_ASSERT**报告类型。 默认情况下，断言失败和错误会定向到调试消息窗口。 [_CrtSetReportMode](crtsetreportmode.md) 和 [_CrtSetReportFile](crtsetreportfile.md) 函数用于为每种报告类型定义目标。

当目标是调试消息窗口且用户单击**重试**按钮， **_CrtDbgReportW**返回 1，从而导致 **_ASSERT_EXPR**， **_断言**并 **_ASSERTE**宏启动调试器，前提是启用了实时 (JIT) 调试。

有关报告过程的详细信息，请参阅 [_CrtDbgReport、_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) 函数。 有关解决断言失败以及将这些宏用作调试错误处理机制的详细信息，请参阅 [使用宏进行验证和报告](/visualstudio/debugger/macros-for-reporting)。

除了 **_ASSERT**宏[断言](assert-macro-assert-wassert.md)宏可以用于验证程序逻辑。 此宏可在这些库的调试和发布版本中使用。 [_RPT、_RPTF](rpt-rptf-rptw-rptfw-macros.md) 调试宏还可用于生成调试报告，但它们不计算表达式。 **_RPT**宏生成一个简单的报表。 **_RPTF**宏生成的报告中包括在其中调用报告宏的源代码文件和行号。 提供了这些宏的宽字符版本 (**_RPTW**， **_RPTFW**)。 宽字符版本与窄字符版本相同，只不过宽字符字符串用于所有字符串参数和输出。

尽管 **_ASSERT_EXPR**， **_ASSERT**并 **_ASSERTE**是宏并且可通过包括\<crtdbg.h >，该应用程序必须与调试链接C 运行时库的版本时 **_DEBUG**定义，因为这些宏调用其他运行时函数。

## <a name="requirements"></a>要求

|宏|必需的标头|
|-----------|---------------------|
|**_ASSERT_EXPR**， **_ASSERT**， **_ASSERTE**|\<crtdbg.h>|

## <a name="example"></a>示例

在此程序中，在调用 **_ASSERT**并 **_ASSERTE**宏，以测试条件`string1 == string2`。 如果条件失败，则这些宏会打印诊断消息。 **_RPT**并 **_RPTF**宏的组中还会执行此程序中，作为一种替代方法**printf**函数。

```C
// crt_ASSERT_macro.c
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug
//
// This program uses the _ASSERT and _ASSERTE debugging macros.
//

#include <stdio.h>
#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

int main()
{
   char *p1, *p2;

   // The Reporting Mode and File must be specified
   // before generating a debug report via an assert
   // or report macro.
   // This program sends all report types to STDOUT.
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);

   // Allocate and assign the pointer variables.
   p1 = (char *)malloc(10);
   strcpy_s(p1, 10, "I am p1");
   p2 = (char *)malloc(10);
   strcpy_s(p2, 10, "I am p2");

   // Use the report macros as a debugging
   // warning mechanism, similar to printf.
   // Use the assert macros to check if the
   // p1 and p2 variables are equivalent.
   // If the expression fails, _ASSERTE will
   // include a string representation of the
   // failed expression in the report.
   // _ASSERT does not include the
   // expression in the generated report.
   _RPT0(_CRT_WARN,
       "Use the assert macros to evaluate the expression p1 == p2.\n");
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);
   _ASSERT(p1 == p2);

   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",
          p1, p2);
   _ASSERTE(p1 == p2);

   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);

   free(p2);
   free(p1);

   return 0;
}
```

```Output
Use the assert macros to evaluate the expression p1 == p2.
crt_ASSERT_macro.c(54) :
Will _ASSERT find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(55) : Assertion failed!
crt_ASSERT_macro.c(58) :

Will _ASSERTE find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2
'I am p1' != 'I am p2'
```

## <a name="see-also"></a>请参阅

[调试例程](../../c-runtime-library/debug-routines.md)<br/>
[assert 宏、_assert、_wassert](assert-macro-assert-wassert.md)<br/>
[_RPT、_RPTF、_RPTW、_RPTFW 宏](rpt-rptf-rptw-rptfw-macros.md)<br/>

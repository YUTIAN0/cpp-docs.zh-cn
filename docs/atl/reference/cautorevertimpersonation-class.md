---
title: CAutoRevertImpersonation 类 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
dev_langs:
- C++
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45a14f8c742393c60a026f7c58217407715ef282
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052729"
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation 类

此类将恢复[CAccessToken](../../atl/reference/caccesstoken-class.md) nonimpersonating 状态时超出范围的对象。

## <a name="syntax"></a>语法

```
class CAutoRevertImpersonation
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|名称|描述|
|----------|-----------------|
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|构造`CAutoRevertImpersonation`对象|
|[CAutoRevertImpersonation:: ~ CAutoRevertImpersonation](#dtor)|销毁该对象并将恢复访问令牌模拟。|

### <a name="public-methods"></a>公共方法

|名称|描述|
|----------|-----------------|
|[CAutoRevertImpersonation::Attach](#attach)|会自动模拟还原操作的访问令牌。|
|[CAutoRevertImpersonation::Detach](#detach)|取消自动模拟还原操作。|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|检索访问令牌当前与此对象相关联。|

## <a name="remarks"></a>备注

[访问令牌](/windows/desktop/SecAuthZ/access-tokens)是一个对象，用于描述进程或线程的安全上下文并分配给每个用户登录到 Windows NT 或 Windows 2000 系统。 这些访问令牌可以用来表示`CAccessToken`类。

此外，有时需要模拟访问令牌。 为方便起见，提供此类，但它不执行模拟的访问令牌;它只能执行到 nonimpersonated 状态自动还原操作。 这是因为令牌访问模拟可以执行多种不同的方式。

有关 Windows 中的访问控制模型的简介，请参阅[访问控制](/windows/desktop/SecAuthZ/access-control)Windows SDK 中。

## <a name="requirements"></a>要求

**标头：** atlsecurity.h

##  <a name="attach"></a>  CAutoRevertImpersonation::Attach

会自动模拟还原操作的访问令牌。

```
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>参数

*PAT*<br/>
地址[CAccessToken](../../atl/reference/caccesstoken-class.md)对象会自动恢复

### <a name="remarks"></a>备注

应仅使用此方法，如果[CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md)对象创建为 null`CAccessToken`指针，或者如果[分离](#detach)以前调用过。 对于简单的情况下，不需要使用此方法。

##  <a name="cautorevertimpersonation"></a>  CAutoRevertImpersonation::CAutoRevertImpersonation

构造 `CAutoRevertImpersonation` 对象。

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>参数

*PAT*<br/>
地址[CAccessToken](../../atl/reference/caccesstoken-class.md)对象会自动恢复。

### <a name="remarks"></a>备注

从，最好创建之前应分别执行访问令牌的实际模拟`CAutoRevertImpersonation`对象。 此模拟会自动还原时`CAutoRevertImpersonation`对象超出范围。

##  <a name="dtor"></a>  CAutoRevertImpersonation:: ~ CAutoRevertImpersonation

销毁该对象并将恢复访问令牌模拟。

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>备注

还原当前生效的任何模拟[CAccessToken](../../atl/reference/caccesstoken-class.md)对象提供在构造时或通过[附加](#attach)方法。 如果没有`CAccessToken`是相关联，析构函数不起作用。

##  <a name="detach"></a>  CAutoRevertImpersonation::Detach

取消自动模拟还原操作。

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>返回值

以前相关联的地址[CAccessToken](../../atl/reference/caccesstoken-class.md)，或如果没有关联已存在，则为 NULL。

### <a name="remarks"></a>备注

调用**分离**阻止`CAutoRevertImpersonation`恢复当前生效的任何模拟对象[CAccessToken](../../atl/reference/caccesstoken-class.md)与此对象关联的对象。 `CAutoRevertImpersonation` 然后可以使用任何影响销毁或重新关联到相同或其他`CAccessToken`对象使用[附加](#attach)。

##  <a name="getaccesstoken"></a>  CAutoRevertImpersonation::GetAccessToken

检索访问令牌当前与此对象相关联。

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>返回值

以前相关联的地址[CAccessToken](../../atl/reference/caccesstoken-class.md)，或如果没有关联已存在，则为 NULL。

### <a name="remarks"></a>备注

如果包括的模拟重新用于调用此方法`CAccessToken`对象，[分离](#detach)应改为使用方法。

## <a name="see-also"></a>请参阅

[ATLSecurity 示例](../../visual-cpp-samples.md)<br/>
[访问令牌](/windows/desktop/SecAuthZ/access-tokens)<br/>
[类概述](../../atl/atl-class-overview.md)

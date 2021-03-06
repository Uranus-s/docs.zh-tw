---
title: ICorDebugManagedCallback::Break 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 621c5b1e32a1a21c2b0b883249c3b65fadceb5f2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632358"
---
# <a name="icordebugmanagedcallbackbreak-method"></a>ICorDebugManagedCallback::Break 方法

會告知偵錯工具時<xref:System.Reflection.Emit.OpCodes.Break>執行指令碼資料流中的。

## <a name="syntax"></a>語法

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a>參數

`pAppDomain`\
[in]ICorDebugAppDomain 物件，表示應用程式定義域，其中包含中斷指令指標。

`thread`\
[in]ICorDebugThread 物件，表示執行緒，其中包含中斷指令指標。

## <a name="requirements"></a>需求

**平台：** 請參閱[系統需求](../../../../docs/framework/get-started/system-requirements.md)。

**標頭：** CorDebug.idl、CorDebug.h

**LIBRARY:** CorGuids.lib

**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>另請參閱

- [ICorDebugManagedCallback 介面](icordebugmanagedcallback-interface.md)

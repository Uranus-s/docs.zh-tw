---
title: GetCachePath 函式
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf23a8f1893aa0f992d554d3c7533c3dc42f4e95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985890"
---
# <a name="getcachepath-function"></a>GetCachePath 函式
取得快取的組件，並使用指定的旗標的路徑。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>參數  
 `dwCacheFlags`  
 [in][ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)值，指出快取的組件的來源。  
  
 `pwzCachePath`  
 [out]至路徑傳回的指標。  
  
 `pcchPath`  
 [in、 out]要求最大長度`pwzCachePath`，並會在傳回時，實際長度時`pwzCachePath`。  
  
## <a name="requirements"></a>需求  
 **平台：** 請參閱[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** Fusion.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱

- [ASM_CACHE_FLAGS 列舉](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)
- [融合全域靜態函式](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)

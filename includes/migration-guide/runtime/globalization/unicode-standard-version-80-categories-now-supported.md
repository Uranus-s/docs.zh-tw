---
ms.openlocfilehash: efa0efaf40e2e432d477f1659d7bde3abc98241d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236018"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>現在支援 Unicode 標準 8.0 版分類

|   |   |
|---|---|
|詳細資料|在 .NET Framework 4.6.2 中，Unicode 資料已從 Unicode 標準 6.3 版升級至 8.0 版。  在 .NET Framework 4.6.2 中要求 Unicode 字元分類時，某些結果可能不符合舊版 .NET Framework 中的結果。  這項變更主要會影響柴羅基文音節和新傣文母音符號和音調標記。|
|建議|請檢閱程式碼，並移除/變更仰賴硬式編碼的 Unicode 字元分類的邏輯。|
|範圍|次要|
|版本|4.6.2|
|類型|執行階段|
|受影響的 API|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|

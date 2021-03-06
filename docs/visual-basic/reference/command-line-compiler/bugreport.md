---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 440e583b55765d680ee72f8574f929e335e10cdb
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590625"
---
# <a name="-bugreport"></a>-bugreport
建立您提出錯誤報告時，您可以使用的檔案。  
  
## <a name="syntax"></a>語法  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a>引數  
  
|詞彙|定義|  
|---|---|  
|`file`|必要項。 將包含錯誤報告的檔案名稱。 將檔案名稱括在引號 ("") 如果名稱包含空格。|  
  
## <a name="remarks"></a>備註  
 下列資訊會新增至`file`:  
  
- 在編譯中的所有原始程式碼檔案的複本。  
  
- 在編譯中使用的編譯器選項的清單。  
  
- 您的編譯器、 通用語言執行平台，以及作業系統的版本資訊。  
  
- 編譯器輸出 (如果有的話)。  
  
- 問題是，系統會提示您的描述。  
  
- 描述您認為問題該如何應該解決，會提示您輸入。  
  
 因為所有原始程式檔的複本包含在`file`，您可能想要重現 （可疑的） 的程式碼缺失最短的程式中。  
  
> [!IMPORTANT]
>  `-bugreport`選項會產生包含潛在的敏感資訊的檔案。 這包括目前的時間，編譯器版本、.NET Framework 版本、 作業系統版本、 使用者名稱、 用編譯器執行的時間、 所有的原始程式碼，以及任何參考的組件的二進位格式的命令列引數。 這個選項可以存取伺服器端編譯的 ASP.NET 應用程式的 Web.config 檔案中指定的命令列選項。 若要避免這個問題，修改 Machine.config 檔案要禁止使用者在伺服器上進行編譯。  
  
 如果這個選項搭配`-errorreport:prompt`， `-errorreport:queue`，或`-errorreport:send`，且您的應用程式遇到編譯器內部錯誤中的資訊`file`傳送給 Microsoft Corporation。 這項資訊可協助 Microsoft 工程師找出錯誤的原因，而且可能有助於改善下一版的 Visual Basic。 根據預設，會不傳送任何資訊給 Microsoft。 不過，當您編譯應用程式使用`-errorreport:queue`、 啟用預設的應用程式會收集其錯誤報告。 然後，當電腦的系統管理員登入時，錯誤報告系統就會顯示快顯視窗，可讓系統管理員以轉寄給 Microsoft 的任何錯誤會報告登入之後發生。  
  
> [!NOTE]
>  `/bugreport`選項不是從 Visual Studio 開發環境中使用; 它是使用只有您在編譯時從命令列。  
  
## <a name="example"></a>範例  
 下列範例會編譯`T2.vb`，然後將錯誤報告的所有資訊都放在檔案中`Problem.txt`。  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>另請參閱

- [Visual Basic 命令列編譯器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-偵錯 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)
- [-errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [編譯命令列範例](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [（ASP.NET 設定結構描述） securityPolicy 的 trustLevel 項目](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))

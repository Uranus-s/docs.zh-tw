---
title: 授權存取服務作業
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: 857e1ebe21dcb37764ddf60570a00ec35b205c8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955003"
---
# <a name="authorizing-access-to-service-operations"></a>授權存取服務作業
這個範例會示範如何使用[ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)若要允許使用<xref:System.Security.Permissions.PrincipalPermissionAttribute>屬性來授權存取服務作業。 此樣本根據[開始使用](../../../../docs/framework/wcf/samples/getting-started-sample.md)範例。 服務和用戶端使用設定[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)。 `mode`的屬性[\<安全性 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)已設為`Message`並`clientCredentialType`已設為`Windows`。 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 會套用至每個服務方法，並且用來限制每個作業的存取。 呼叫者必須是 Windows 系統管理員才能存取每個作業。  
  
 在這個範例中，用戶端是主控台應用程式 (.exe)，而服務則是由網際網路資訊服務 (IIS) 所裝載。  
  
> [!NOTE]
>  此範例的安裝程序與建置指示位於本主題的結尾。  
  
 服務組態檔會使用[ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)若要設定`principalPermissionMode`屬性：  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>   
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 將 `principalPermissionMode` 設定為 `UseWindowsGroups`，便可以根據 Windows 群組名稱來使用 <xref:System.Security.Permissions.PrincipalPermissionAttribute>。  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 會套用至每個作業以要求呼叫者必須是 Windows Administrators 群組的成員，如下列範例程式碼所示。  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,   
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 當您執行範例時，作業要求和回應會顯示在用戶端主控台視窗中。 如果用戶端是以 Administrators 群組成員的帳戶執行，該用戶端便能與每個作業進行成功通訊，否則就會拒絕存取。 為了體驗授權失敗，這時要使用不屬於 Administrators 群組的帳戶來執行用戶端。 在主控台視窗中按 ENTER 鍵，即可關閉用戶端。  
  
 藉由實作 <xref:System.ServiceModel.Dispatcher.IErrorHandler>，即可向服務通知授權失敗。 請參閱[擴充控制項透過錯誤處理和報告](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)如需實作資訊`IErrorHandler`。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>若要安裝、建置及執行範例  
  
1. 請確定您已執行[Windows Communication Foundation 範例的單次安裝程序](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要建置方案的 C# 或 Visual Basic .NET 版本，請遵循 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的指示。  
  
3. 若要在單一或跨電腦組態中執行範例，請依照下列中的指示[執行 Windows Communication Foundation 範例](../../../../docs/framework/wcf/samples/running-the-samples.md)。  

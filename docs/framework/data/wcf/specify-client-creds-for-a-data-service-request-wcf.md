---
title: HOW TO：指定用戶端認證，資料服務要求 (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 1632f9af-e45f-4363-9222-03823daa8e28
ms.openlocfilehash: ed32cb7d1c9da8a98333bc7eddd3e5707e4664ff
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "64660870"
---
# <a name="how-to-specify-client-credentials-for-a-data-service-request-wcf-data-services"></a>HOW TO：指定用戶端認證，資料服務要求 (WCF Data Services)
預設情況下，將要求傳送至 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 服務時，用戶端程式庫不提供認證。 不過，您可以透過為 <xref:System.Net.NetworkCredential> 的 <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A> 屬性提供 <xref:System.Data.Services.Client.DataServiceContext>，藉以指定要傳送的認證來驗證要求。 如需詳細資訊，請參閱 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)。 本主題中的範例會示範如何在從資料服務要求資料時，明確地提供 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 用戶端所使用的認證。  
  
 本主題中的範例使用 Northwind 範例資料服務和自動產生的用戶端資料服務類別。 當您完成建立這項服務和用戶端資料類別[WCF Data Services 快速入門](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。 您也可以使用[Northwind 範例資料服務](https://go.microsoft.com/fwlink/?LinkId=187426)上發行的[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]網站; 此範例資料服務是唯讀的並在嘗試儲存變更傳回錯誤。 範例資料服務上[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]網站允許匿名驗證。  
  
## <a name="example"></a>範例  
 下列範例是從 Windows Presentation Framework 應用程式的主頁面的 Extensible Application Markup Language (XAML) 檔案的程式碼後置頁面。 此範例會顯示 `LoginWindow` 執行個體，以便向使用者收集驗證認證，然後在要求資料服務時使用這些認證。  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentials.xaml.cs#clientcredentials)]  
 [!code-vb[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/clientcredentials.xaml.vb#clientcredentials)]
  
## <a name="example"></a>範例  
 下列 XAML 定義 WPF 應用程式的主頁面。  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentials.xaml#clientcredentialsxaml)]  
  
## <a name="example"></a>範例  
 下列範例取自視窗的程式碼後置頁面，在要求資料服務前，此視窗用來收集使用者的驗證認證。  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentialslogin.xaml.cs#clientcredentialslogin)]  
 [!code-vb[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/clientcredentialslogin.xaml.vb#clientcredentialslogin)]
  
## <a name="example"></a>範例  
 下列 XAML 定義 WPF 應用程式的登入。  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsLoginXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/clientcredentialslogin.xaml#clientcredentialsloginxaml)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 下列安全性考量適用於本主題中的範例：  
  
- 若要驗證此範例中提供的認證有效，Northwind 資料服務必須使用匿名存取以外的驗證配置。 否則，主控資料服務的網站將不會要求認證。  
  
- 使用者認證只有在執行期間才會要求，而且不得快取。 認證永遠必須以安全的方式儲存。  
  
- 使用基本與摘要式驗證傳送的資料不會經過加密，因此敵人可以看到資料。 此外，基本驗證認證 (使用者名稱和密碼) 會以純文字傳送，而且可以被攔截。  
  
 如需詳細資訊，請參閱 [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)。  
  
## <a name="see-also"></a>另請參閱

- [保護 WCF 資料服務的安全](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)
- [WCF Data Services 用戶端程式庫](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

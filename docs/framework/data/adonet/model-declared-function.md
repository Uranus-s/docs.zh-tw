---
title: 模型宣告函式
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: a0bea36693122c77d9c1abdf4484ee8e68627a0c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645857"
---
# <a name="model-declared-function"></a>模型宣告函式
A*模型宣告函式*是宣告在概念模型中，但該概念模型中未定義的函式。 該函式可能是在裝載或儲存環境中定義的。 例如，模型宣告函式可能對應到在資料庫中定義的函式，因而在概念模型中公開伺服器端的功能。  
  
 模型宣告函式的宣告包含下列資訊：  
  
- 函式的名稱。 (必要項)  
  
- 傳回值的型別。 (選擇項)  
  
    > [!NOTE]
    >  若未指定任何傳回值，則傳回型別為 void。  
  
- 參數資訊，包括參數名稱和型別。 (選擇項)  
  
## <a name="example"></a>範例  
 [ADO.NET Entity Framework](./ef/index.md)會使用稱為概念結構定義語言的特定領域語言 (DSL) ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) 來定義概念模型。 在 CSDL 中，模型宣告函式的其中一個實作是函式匯入 (使用[FunctionImport 項目](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl))。 下列 CSDL 定義具有函式匯入定義的實體容器。 請注意，由於沒有指定傳回型別，因此該函式的傳回型別為 void。  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>另請參閱

- [實體資料模型索引鍵概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [實體資料模型](../../../../docs/framework/data/adonet/entity-data-model.md)

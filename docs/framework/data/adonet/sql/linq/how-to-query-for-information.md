---
title: HOW TO：查詢資訊
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: aedf89f1e570b34d31050fabb91842cefe351488
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033731"
---
# <a name="how-to-query-for-information"></a>HOW TO：查詢資訊
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中之查詢使用的語法與 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中的查詢相同。 唯一的差別在於中參考的物件[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]查詢都會對應到資料庫中的項目。 如需詳細資訊，請參閱 [LINQ 查詢簡介 (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)。  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 會將您撰寫的查詢轉譯為對等 SQL 查詢，並將它們傳送給伺服器進行處理。  
  
 在 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 應用程式中，可能需要特別注意 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查詢的部分功能。 如需詳細資訊，請參閱 <<c0> [ 查詢概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)。  
  
## <a name="example"></a>範例  
 下列查詢會要求來自倫敦 (London) 的客戶名單。 在這個範例中，`Customers` 是 Northwind 範例資料庫中的資料表。  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>另請參閱

- [建立物件模型](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [下載範例資料庫](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [查詢資料庫](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)

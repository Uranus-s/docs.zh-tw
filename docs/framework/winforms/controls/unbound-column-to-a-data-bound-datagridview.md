---
title: HOW TO：將未繫結資料行新增至已繫結資料的 Windows Forms DataGridView 控制項
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: d40eea54d908f17fc2fe893d5bc15a073a066ba1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651583"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a>HOW TO：將未繫結資料行新增至已繫結資料的 Windows Forms DataGridView 控制項
您在 <xref:System.Windows.Forms.DataGridView> 控制項中顯示的資料，通常來自於某種的資料來源，但您可能想要顯示不是來自資料來源之資料的資料行。 這種資料行稱為未繫結資料行。 未繫結資料行可以有許多形式。 通常，它們用來提供資料列詳細資料的存取權。  
  
 下列程式碼範例示範如何建立未繫結的資料行**詳細資料**實作主從式案例時，父資料表中的特定資料列與按鈕，以顯示子資料表。 若要回應按下按鈕後，實作 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 事件處理常式，其顯示包含子資料表的表單。  
  
 在 Visual Studio 中會支援這項工作。  另請參閱[How to:新增和移除資料行中的 Windows Form DataGridView 控制項使用設計工具](add-and-remove-columns-in-the-datagrid-using-the-designer.md)。  
  
## <a name="example"></a>範例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 這個範例需要：  
  
- 名為 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控制項。  
  
- <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 組件的參考。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Forms.DataGridView>
- [在 Windows Forms DataGridView 控制項中顯示資料](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Windows Forms DataGridView 控制項的資料顯示模式](data-display-modes-in-the-windows-forms-datagridview-control.md)

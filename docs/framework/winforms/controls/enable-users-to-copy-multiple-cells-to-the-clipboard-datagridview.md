---
title: HOW TO：讓使用者將 Windows Forms DataGridView 控制項的多個儲存格複製到剪貼簿
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: b220603adcaeae6f3380a2e3c10ea524c9a61f24
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591916"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a>作法：讓使用者將 Windows Forms DataGridView 控制項的多個儲存格複製到剪貼簿
當您啟用儲存格複製時，會使其他應用程式可以透過 <xref:System.Windows.Forms.Clipboard> 輕易存取 <xref:System.Windows.Forms.DataGridView> 控制項中的資料。 選取之儲存格的值會轉換為字串，並加入剪貼簿，針對 [記事本] 和 Excel 等應用程式以 Tab 鍵分隔文字值貼入，而針對 Word 等應用程式以 HTML 格式資料表貼入。  
  
 您可以將儲存格複製設定為僅複製儲存格的值、包含剪貼簿資料中的資料列和資料行標頭文字，或僅在使用者選取整個資料列或資料行時包含標頭文字。  
  
 根據選取模式，使用者可以選取多個儲存格的離線群組。 當使用者複製儲存格至剪貼簿時，並不會複製未有選取之儲存格的資料列和資料行。 所有其他資料列或資料行會變成複製到剪貼簿之資料的資料表中的資料列和資料行。 這些資料列或資料行中的未選取儲存格會以空白預留位置複製到剪貼簿。  
  
### <a name="to-enable-cell-copying"></a>若要啟用儲存格複製  
  
- 設定 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> 屬性。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a>範例  
 下列完整的程式碼範例示範儲存格如何複製到剪貼簿。 此範例包含一個按鈕，會使用 <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> 方法將選取的儲存格複製到剪貼簿，並在文字方塊中顯示剪貼簿的內容。  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 此程式碼需要：  
  
- N:System 和 N:System.Windows.Forms 組件的參考。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [選取範圍和剪貼簿與 Windows Forms DataGridView 控制項搭配使用](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)

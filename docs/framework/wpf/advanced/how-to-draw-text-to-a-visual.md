---
title: HOW TO：在視覺效果繪製文字
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: 1ea31540ad59ab419e209e4133bcb88640cc01fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776164"
---
# <a name="how-to-draw-text-to-a-visual"></a>HOW TO：在視覺效果繪製文字
下列範例示範如何繪製文字至<xref:System.Windows.Media.DrawingVisual>使用<xref:System.Windows.Media.DrawingContext>物件。 繪製的內容由呼叫<xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>方法的<xref:System.Windows.Media.DrawingVisual>物件。 您可以繪製圖形和文字，放入繪圖內容。  
  
 若要繪製文字至繪製內容，請使用<xref:System.Windows.Media.DrawingContext.DrawText%2A>方法的<xref:System.Windows.Media.DrawingContext>物件。 當您完成繪製至繪圖內容的內容時，呼叫<xref:System.Windows.Media.DrawingContext.Close%2A>方法來關閉繪製內容並保存內容。  
  
## <a name="example"></a>範例  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  如需先前程式碼範例出處的完整程式碼範例，請參閱[使用 DrawingVisuals 進行點擊測試範例 (英文)](https://go.microsoft.com/fwlink/?LinkID=159994)。

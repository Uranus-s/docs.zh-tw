---
title: HOW TO：在 Visual Basic 中使用 StringBuilder 建立字串
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 00fefcc138164288d872cd339f165dc6ffc0131a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032120"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a>HOW TO：在 Visual Basic 中使用 StringBuilder 建立字串
此範例會建構從許多較小的字串，使用一長串<xref:System.Text.StringBuilder>類別。 <xref:System.Text.StringBuilder>類別的效率高於`&=`將許多字串串連運算子。  
  
## <a name="example"></a>範例  
 下列範例建立的執行個體<xref:System.Text.StringBuilder>類別，將 1000 的字串附加至該執行個體，並接著會傳回它的字串表示。  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a>另請參閱

- [使用 StringBuilder 類別](../../../../standard/base-types/stringbuilder.md)
- [&= 運算子](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [字串](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [建立新字串](../../../../standard/base-types/creating-new.md)
- [操作字串](../../../../standard/base-types/manipulating-strings.md)

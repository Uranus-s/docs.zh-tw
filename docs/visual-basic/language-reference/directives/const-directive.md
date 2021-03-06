---
title: '#Const 指示詞 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 5458bbebc6064eb6273b8deb5447b8941e1d233f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746677"
---
# <a name="const-directive"></a>#Const 指示詞
適用於 Visual Basic 中定義條件式編譯器常數。  
  
## <a name="syntax"></a>語法  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a>組件  
 `constname`  
 必要項。 所定義的常數名稱。  
  
 `expression`  
 必要項。 常值、 條件式編譯器常數或任何組合，包括任何或所有算術或邏輯運算子，除了`Is`。  
  
## <a name="remarks"></a>備註  
 條件式編譯器常數一律是以其出現的檔案公開的。 您無法建立使用的公用編譯器常數`#Const`指示詞; 您可以只在使用者介面，或與建立它們`/define`編譯器選項。  
  
 您只能使用條件式編譯器常數和常值中的`expression`。 使用標準的常數，以定義`Const`會造成錯誤。 相反地，您可以使用常數定義`#Const`條件式編譯的關鍵字。 常數也可以定義，在此情況下，它們的值為`Nothing`。  
  
## <a name="example"></a>範例  
 此範例使用 `#Const` 指示詞。  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>另請參閱

- [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [#If...Then...#Else 指示詞](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Const 陳述式](../../../visual-basic/language-reference/statements/const-statement.md)
- [條件式編譯](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [If...Then...Else 陳述式](../../../visual-basic/language-reference/statements/if-then-else-statement.md)

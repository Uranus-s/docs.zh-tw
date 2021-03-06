---
title: 物件變數值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: c17c5f85952596f0a080ca473e8f792740e66b8f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054181"
---
# <a name="object-variable-values-visual-basic"></a>物件變數值 (Visual Basic)
變數[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)可以參考任何類型的資料。 值，您將儲存在`Object`變數保留在其他地方在記憶體中，而本身的變數存放資料的指標。  
  
## <a name="object-classifier-functions"></a>物件的分類函數  
 Visual Basic 提供傳回什麼的相關資訊的函式`Object`變數會參照到下, 表所示。  
  
|功能|如果物件變數參考，則傳回 True|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|值，而不是單一值的陣列|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|A[日期資料型別](../../../../visual-basic/language-reference/data-types/date-data-type.md)值或可以解譯為日期和時間值的字串|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|型別的物件<xref:System.DBNull>，以表示遺失或不存在的資料|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|例外狀況物件，它是衍生自 <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Nothing](../../../../visual-basic/language-reference/nothing.md)，亦即，如果沒有物件目前指派給變數|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|數字或可以解譯為數字的字串|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|參考類型 （例如字串、 陣列、 委派或類別類型）|  
  
 您可以使用這些函式，以避免送出至操作或程序無效的值。  
  
## <a name="typeof-operator"></a>TypeOf 運算子  
 您也可以使用[TypeOf 運算子](../../../../visual-basic/language-reference/operators/typeof-operator.md)來判斷是否為物件變數目前會參考在特定資料型別。 `TypeOf`...`Is`運算式會評估為`True`如果運算元的執行階段類型衍生自或實作指定的型別。  
  
 下列範例會使用`TypeOf`指的值和參考類型的物件變數上。  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 上述範例會將下列行以**偵錯**視窗：  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 物件變數`num`類型的資料是指`Integer`，並`frm`類別的物件是指<xref:System.Windows.Forms.Form>。  
  
## <a name="object-arrays"></a>物件陣列  
 您可以宣告並使用陣列`Object`變數。 當您需要處理各種資料類型和物件類別時，這非常有用。 陣列中的所有項目必須具有相同的宣告的資料類型。 宣告為此資料型別`Object`可讓您儲存物件和類別以及陣列中其他資料類型的執行個體。  
  
## <a name="see-also"></a>另請參閱

- [物件變數](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [物件變數宣告](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [物件變數指派](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [如何：參考物件的目前執行個體](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [如何：決定物件變數參考的類型](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [如何：判斷兩個物件是否關聯](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [如何：判斷兩個物件是否相同](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [資料類型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)

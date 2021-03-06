---
title: HOW TO：啟用 Windows Forms RichTextBox 控制項的拖放作業
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
ms.openlocfilehash: 5c60fe411fcbf6257c8aaacf1f7400c11c150ddc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972129"
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a>HOW TO：啟用 Windows Forms RichTextBox 控制項的拖放作業
使用 Windows Forms <xref:System.Windows.Forms.RichTextBox> 控制項的拖放作業，可藉由處理 <xref:System.Windows.Forms.RichTextBox.DragEnter> 和 <xref:System.Windows.Forms.RichTextBox.DragDrop> 事件來完成。 因此，使用 <xref:System.Windows.Forms.RichTextBox> 控制項進行拖放作業相當簡單。  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a>在 RichTextBox 控制項中啟用拖曳作業  
  
1. 將 <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> 控制項的 <xref:System.Windows.Forms.RichTextBox> 屬性設為 `true`。  
  
2. 在 <xref:System.Windows.Forms.RichTextBox.DragEnter> 事件的事件處理常式中撰寫程式碼。 使用 `if` 陳述式，以確認拖曳中的資料是屬於可接受的類型 (在此例中為文字)。 <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> 屬性可以設定為 <xref:System.Windows.Forms.DragDropEffects> 列舉的任何值。  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     (Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 下列程式碼置於表單的建構函式，以註冊事件處理常式。  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3. 撰寫程式碼來處理 <xref:System.Windows.Forms.RichTextBox.DragDrop> 事件。 使用 <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> 方法來擷取正在拖曳的資料。  
  
     在以下範例中，程式碼會將 <xref:System.Windows.Forms.RichTextBox.Text%2A> 控制項的 <xref:System.Windows.Forms.RichTextBox> 屬性設為等於正在拖曳的資料。 如果 <xref:System.Windows.Forms.RichTextBox> 控制項中已有文字，拖曳的文字會插入在插入點。  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragDrop  
       Dim i As Int16   
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +   
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());   
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     (Visual C# 和[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 下列程式碼置於表單的建構函式，以註冊事件處理常式。  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew   
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a>測試應用程式中的拖放功能  
  
1. 儲存並建置您的應用程式。 在執行時，執行 WordPad。  
  
     WordPad 是由允許拖放作業之 Windows 所安裝的文字編輯器。 存取方式是按一下 [開始]  按鈕、選取 [執行] ，然後在 [執行] `WordPad`**對話方塊中的文字方塊中輸入** 並按一下 [確定] 。  
  
2. 一旦開啟 WordPad，請於其中輸入文字的字串。 使用滑鼠、選取文字，然後再將選取的文字拖曳到 Windows 應用程式中的 <xref:System.Windows.Forms.RichTextBox> 控制項。  
  
     請注意，當滑鼠指向 <xref:System.Windows.Forms.RichTextBox> 控制項 (然後因此引發 <xref:System.Windows.Forms.RichTextBox.DragEnter> 事件) 時，滑鼠指標會變更，且您可以將選取的文字放到 <xref:System.Windows.Forms.RichTextBox> 控制項。  
  
     當您放開滑鼠按鈕時，會放下選取的文字 (也就是，會引發 <xref:System.Windows.Forms.RichTextBox.DragDrop> 事件)，並插入 <xref:System.Windows.Forms.RichTextBox> 控制項內。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Forms.RichTextBox>
- [如何：執行應用程式之間的拖放作業](../advanced/how-to-perform-drag-and-drop-operations-between-applications.md)
- [RichTextBox 控制項](richtextbox-control-windows-forms.md)
- [在 Windows Forms 上使用的控制項](controls-to-use-on-windows-forms.md)

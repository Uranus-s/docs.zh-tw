---
title: '例外狀況: failwith 函式'
description: 了解如何 'failwith' 函式會產生F#例外狀況。
ms.date: 05/16/2016
ms.openlocfilehash: 08107966ddc2f55625347deb92d224b286df7761
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641955"
---
# <a name="exceptions-the-failwith-function"></a>例外狀況: failwith 函式

`failwith`函式會產生F#例外狀況。

## <a name="syntax"></a>語法

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>備註

*錯誤訊息字串*在先前的語法是字串常值或型別的值`string`。 它會變成`Message`例外狀況的屬性。

所產生的例外狀況`failwith`已`System.Exception`例外狀況，也就是具有名稱的參考`Failure`在F#程式碼。 下列程式碼說明如何使用`failwith`擲回例外狀況。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>另請參閱

- [例外狀況處理](index.md)
- [例外狀況類型](exception-types.md)
- [例外狀況：`try...with`運算式](the-try-with-expression.md)
- [例外狀況：`try...finally`運算式](the-try-finally-expression.md)
- [例外狀況：`raise` 函式](the-raise-function.md)

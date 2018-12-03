---
title: 類別和物件 - C# 教學課程簡介
description: 建立您的第一個 C# 程式並探索物件導向概念
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 8b823e05ea5e51bb3096d6a0611630c996f56b33
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205357"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="2900e-103">探索使用類別與物件的物件導向程式設計</span><span class="sxs-lookup"><span data-stu-id="2900e-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="2900e-104">此教學課程要求您必須有可用於開發的電腦。</span><span class="sxs-lookup"><span data-stu-id="2900e-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="2900e-105">.NET 主題[只要 10 分鐘立即上手](https://www.microsoft.com/net/core) \(英文\) 中有關於在 Mac、PC 或 Linux 上設定本機開發環境的指示。</span><span class="sxs-lookup"><span data-stu-id="2900e-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="2900e-106">您可以在[熟悉開發工具](local-environment.md)中快速檢視將會用到的命令，並取得可提供詳細資料的連結。</span><span class="sxs-lookup"><span data-stu-id="2900e-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="2900e-107">建立您的應用程式</span><span class="sxs-lookup"><span data-stu-id="2900e-107">Create your application</span></span>

<span data-ttu-id="2900e-108">使用終端機視窗，建立名為 **classes** 的目錄。</span><span class="sxs-lookup"><span data-stu-id="2900e-108">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="2900e-109">您將在該目錄建立應用程式。</span><span class="sxs-lookup"><span data-stu-id="2900e-109">You'll build your application there.</span></span> <span data-ttu-id="2900e-110">在主控台視窗中變更至該目錄並輸入 `dotnet new console`。</span><span class="sxs-lookup"><span data-stu-id="2900e-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="2900e-111">這個命令會建立您的應用程式。</span><span class="sxs-lookup"><span data-stu-id="2900e-111">This command creates your application.</span></span> <span data-ttu-id="2900e-112">開啟 **Program.cs**。</span><span class="sxs-lookup"><span data-stu-id="2900e-112">Open **Program.cs**.</span></span> <span data-ttu-id="2900e-113">內容應該看起來如下：</span><span class="sxs-lookup"><span data-stu-id="2900e-113">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="2900e-114">在此教學課程中，您將建立代表銀行帳戶的新型別。</span><span class="sxs-lookup"><span data-stu-id="2900e-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="2900e-115">開發人員通常會在不同的文字檔中定義每個類別。</span><span class="sxs-lookup"><span data-stu-id="2900e-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="2900e-116">隨著程式大小增加，這麼做會使它更易於管理。</span><span class="sxs-lookup"><span data-stu-id="2900e-116">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="2900e-117">在 **classes** 目錄中，建立名為 **BankAccount.cs** 的新檔案。</span><span class="sxs-lookup"><span data-stu-id="2900e-117">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="2900e-118">這個檔案會包含***銀行帳戶***的定義。</span><span class="sxs-lookup"><span data-stu-id="2900e-118">This file will contain the definition of a ***bank account***.</span></span> <span data-ttu-id="2900e-119">物件導向程式設計會以***類別***的形式建立類型來組織程式碼。</span><span class="sxs-lookup"><span data-stu-id="2900e-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="2900e-120">這些類別包含代表特定實體的程式碼。</span><span class="sxs-lookup"><span data-stu-id="2900e-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="2900e-121">`BankAccount` 類別代表銀行帳戶。</span><span class="sxs-lookup"><span data-stu-id="2900e-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="2900e-122">程式碼會透過方法和屬性來實作特定的作業。</span><span class="sxs-lookup"><span data-stu-id="2900e-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="2900e-123">在此教學課程中，銀行帳戶支援此行為：</span><span class="sxs-lookup"><span data-stu-id="2900e-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="2900e-124">它具有能唯一識別銀行帳戶的 10 位數數字。</span><span class="sxs-lookup"><span data-stu-id="2900e-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="2900e-125">它具有能儲存擁有者一個或多個名稱的字串。</span><span class="sxs-lookup"><span data-stu-id="2900e-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="2900e-126">可擷取餘額。</span><span class="sxs-lookup"><span data-stu-id="2900e-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="2900e-127">它接受存款。</span><span class="sxs-lookup"><span data-stu-id="2900e-127">It accepts deposits.</span></span>
1. <span data-ttu-id="2900e-128">它接受提款。</span><span class="sxs-lookup"><span data-stu-id="2900e-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="2900e-129">初始餘額必須為正數。</span><span class="sxs-lookup"><span data-stu-id="2900e-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="2900e-130">提款不可使餘額成為負數。</span><span class="sxs-lookup"><span data-stu-id="2900e-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="2900e-131">定義銀行帳戶類型</span><span class="sxs-lookup"><span data-stu-id="2900e-131">Define the bank account type</span></span>

<span data-ttu-id="2900e-132">您可以從建立能定義該行為之類別的基礎項目來開始。</span><span class="sxs-lookup"><span data-stu-id="2900e-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="2900e-133">內容應該看起來如下：</span><span class="sxs-lookup"><span data-stu-id="2900e-133">It would look like this:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

<span data-ttu-id="2900e-134">在繼續之前，讓我們先查看您所建置的內容。</span><span class="sxs-lookup"><span data-stu-id="2900e-134">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="2900e-135">`namespace` 宣告能提供以邏輯方式組織程式碼的方式。</span><span class="sxs-lookup"><span data-stu-id="2900e-135">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="2900e-136">此教學課程的規模相對較小，所以您會將所有程式碼置於一個命名空間。</span><span class="sxs-lookup"><span data-stu-id="2900e-136">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="2900e-137">`public class BankAccount` 能定義您要建立的類別 (或類型)。</span><span class="sxs-lookup"><span data-stu-id="2900e-137">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="2900e-138">類別宣告後面的 `{` 和 `}` 之內的所有內容，皆定義該類別的行為。</span><span class="sxs-lookup"><span data-stu-id="2900e-138">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="2900e-139">`BankAccount` 類別有五個***成員***。</span><span class="sxs-lookup"><span data-stu-id="2900e-139">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="2900e-140">前三個為***屬性***。</span><span class="sxs-lookup"><span data-stu-id="2900e-140">The first three are ***properties***.</span></span> <span data-ttu-id="2900e-141">屬性是資料元素，且可以具有強制執行驗證或其他規則的程式碼。</span><span class="sxs-lookup"><span data-stu-id="2900e-141">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="2900e-142">後兩個為***方法***。</span><span class="sxs-lookup"><span data-stu-id="2900e-142">The last two are ***methods***.</span></span> <span data-ttu-id="2900e-143">方法是執行單一函式的程式碼區塊。</span><span class="sxs-lookup"><span data-stu-id="2900e-143">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="2900e-144">閱讀每個成員的名稱，應該能提供足夠的資訊，以供您或其他開發人員了解該類別的功能。</span><span class="sxs-lookup"><span data-stu-id="2900e-144">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="2900e-145">開啟新帳戶</span><span class="sxs-lookup"><span data-stu-id="2900e-145">Open a new account</span></span>

<span data-ttu-id="2900e-146">第一個要實作的功能是開啟一個銀行帳戶。</span><span class="sxs-lookup"><span data-stu-id="2900e-146">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="2900e-147">當客戶開啟帳戶時，他們必須提供初始餘額，以及該帳戶的一或多個擁有者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2900e-147">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="2900e-148">建立一個 `BankAccount` 類型的新物件，表示定義一個能指派那些值的***建構函式***。</span><span class="sxs-lookup"><span data-stu-id="2900e-148">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="2900e-149">***建構函式***是具有和該類別相同名稱的成員。</span><span class="sxs-lookup"><span data-stu-id="2900e-149">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="2900e-150">它是用來初始化該類別類型的物件。</span><span class="sxs-lookup"><span data-stu-id="2900e-150">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="2900e-151">將下列建構函式新增到 `BankAccount` 類型：</span><span class="sxs-lookup"><span data-stu-id="2900e-151">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="2900e-152">當您使用 [`new`](../../language-reference/keywords/new.md) 建立物件時，系統便會呼叫建構函式。</span><span class="sxs-lookup"><span data-stu-id="2900e-152">Constructors are called when you create an object using [`new`](../../language-reference/keywords/new.md).</span></span> <span data-ttu-id="2900e-153">以下列行取代 ***program.cs*** 中的 `Console.WriteLine("Hello World!");` 行 (以您的名字取代 `<name>`)：</span><span class="sxs-lookup"><span data-stu-id="2900e-153">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="2900e-154">輸入 `dotnet run` 看看會發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="2900e-154">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="2900e-155">您是否注意到帳戶號碼是空白的？</span><span class="sxs-lookup"><span data-stu-id="2900e-155">Did you notice that the account number is blank?</span></span> <span data-ttu-id="2900e-156">讓我們來修正此情況。</span><span class="sxs-lookup"><span data-stu-id="2900e-156">It's time to fix that.</span></span> <span data-ttu-id="2900e-157">帳戶號碼應該要在物件建構時指派。</span><span class="sxs-lookup"><span data-stu-id="2900e-157">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="2900e-158">但帳戶號碼不應該由呼叫者負責建立。</span><span class="sxs-lookup"><span data-stu-id="2900e-158">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="2900e-159">`BankAccount` 類別程式碼應該要知道如何指派新的帳戶號碼。</span><span class="sxs-lookup"><span data-stu-id="2900e-159">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="2900e-160">最簡單的方法是以 10 位數的數字開始。</span><span class="sxs-lookup"><span data-stu-id="2900e-160">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="2900e-161">建立每個新帳戶時就增加它。</span><span class="sxs-lookup"><span data-stu-id="2900e-161">Increment it when each new account is created.</span></span> <span data-ttu-id="2900e-162">最後，在物件完成建構時儲存目前的帳戶號碼。</span><span class="sxs-lookup"><span data-stu-id="2900e-162">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="2900e-163">將下列成員宣告新增到 `BankAccount` 類別：</span><span class="sxs-lookup"><span data-stu-id="2900e-163">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="2900e-164">這是一個資料成員。</span><span class="sxs-lookup"><span data-stu-id="2900e-164">This is a data member.</span></span> <span data-ttu-id="2900e-165">它是 `private`，這表示它只能由 `BankAccount` 類別中的程式碼存取。</span><span class="sxs-lookup"><span data-stu-id="2900e-165">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="2900e-166">這是將公開責任 (例如具有帳戶號碼) 和私用實作 (帳戶號碼產生的方式) 區隔開來的方法。它也是 `static`，這表示它是由所有 ``BankAccount`` 物件共用的。</span><span class="sxs-lookup"><span data-stu-id="2900e-166">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) It is also `static`, which means it is shared by all of the ``BankAccount`` objects.</span></span> <span data-ttu-id="2900e-167">非靜態變數的值對於每個 ``BankAccount`` 物件的執行個體而言都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="2900e-167">The value of a non-static variable is unique to each instance of the ``BankAccount`` object.</span></span> <span data-ttu-id="2900e-168">將下列兩行新增到建構函式來指派帳戶號碼：</span><span class="sxs-lookup"><span data-stu-id="2900e-168">Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="2900e-169">輸入 `dotnet run` 來查看結果。</span><span class="sxs-lookup"><span data-stu-id="2900e-169">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="2900e-170">建立存款和提款</span><span class="sxs-lookup"><span data-stu-id="2900e-170">Create deposits and withdrawals</span></span>

<span data-ttu-id="2900e-171">您的銀行帳戶必須能接受存款及提款，才算能正常運作。</span><span class="sxs-lookup"><span data-stu-id="2900e-171">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="2900e-172">讓我們透過建立帳戶每一筆交易的日誌，來實作存款和提款。</span><span class="sxs-lookup"><span data-stu-id="2900e-172">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="2900e-173">相較於單純地在每次交易時更新餘額，建立日誌能提供數個好處。</span><span class="sxs-lookup"><span data-stu-id="2900e-173">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="2900e-174">該記錄可用來對所有交易進行稽核，以及管理每日餘額。</span><span class="sxs-lookup"><span data-stu-id="2900e-174">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="2900e-175">藉由在必要時計算所有交易記錄的餘額，在任何單一交易中已修正的錯誤都會正確地在下一次計算中反映出來。</span><span class="sxs-lookup"><span data-stu-id="2900e-175">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="2900e-176">讓我們從建立代表交易的新類型開始。</span><span class="sxs-lookup"><span data-stu-id="2900e-176">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="2900e-177">這是一個不具任何責任的簡單類型。</span><span class="sxs-lookup"><span data-stu-id="2900e-177">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="2900e-178">它需要幾個屬性。</span><span class="sxs-lookup"><span data-stu-id="2900e-178">It needs a few properties.</span></span> <span data-ttu-id="2900e-179">建立名為 ***Transaction.cs*** 的新檔案。</span><span class="sxs-lookup"><span data-stu-id="2900e-179">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="2900e-180">將下列程式碼加入該檔案：</span><span class="sxs-lookup"><span data-stu-id="2900e-180">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="2900e-181">現在，讓我們將 `Transaction` 物件的 <xref:System.Collections.Generic.List%601> 新增到 `BankAccount` 類別。</span><span class="sxs-lookup"><span data-stu-id="2900e-181">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="2900e-182">新增下列宣告：</span><span class="sxs-lookup"><span data-stu-id="2900e-182">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="2900e-183"><xref:System.Collections.Generic.List%601> 類別需要您匯入不同的命名空間。</span><span class="sxs-lookup"><span data-stu-id="2900e-183">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="2900e-184">將下列內容新增到 **BankAccount.cs** 的開頭：</span><span class="sxs-lookup"><span data-stu-id="2900e-184">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="2900e-185">現在，讓我們變更 `Balance` 的報告方式。</span><span class="sxs-lookup"><span data-stu-id="2900e-185">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="2900e-186">報告可以透過針對所有交易的值進行加總來取得。</span><span class="sxs-lookup"><span data-stu-id="2900e-186">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="2900e-187">將 `BankAccount` 類別中 `Balance` 的宣告修改成如下內容：</span><span class="sxs-lookup"><span data-stu-id="2900e-187">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="2900e-188">此範例顯示出***屬性***的一個重要層面。</span><span class="sxs-lookup"><span data-stu-id="2900e-188">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="2900e-189">現在您會在另一個程式要求餘額時計算該值。</span><span class="sxs-lookup"><span data-stu-id="2900e-189">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="2900e-190">您的計算會列舉所有交易，並提供總和作為目前的餘額。</span><span class="sxs-lookup"><span data-stu-id="2900e-190">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="2900e-191">接下來，請實作 `MakeDeposit` 和 `MakeWithdrawal` 方法。</span><span class="sxs-lookup"><span data-stu-id="2900e-191">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="2900e-192">這些方法會強制執行最後兩個規則：初始餘額必須為正數，且所有提款都不能產生負數的餘額。</span><span class="sxs-lookup"><span data-stu-id="2900e-192">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="2900e-193">這也引進了***例外狀況***的概念。</span><span class="sxs-lookup"><span data-stu-id="2900e-193">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="2900e-194">這是指出方法若無法完成其工作便應擲回例外狀況的標準方法。</span><span class="sxs-lookup"><span data-stu-id="2900e-194">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="2900e-195">例外狀況的類型和與它相關的訊息會描述該錯誤。</span><span class="sxs-lookup"><span data-stu-id="2900e-195">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="2900e-196">在這裡，如果存款的金額是負數，`MakeDeposit` 方法便會擲回例外狀況。</span><span class="sxs-lookup"><span data-stu-id="2900e-196">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="2900e-197">如果提款金額是負數，或如果套用提款金額會造成負數的餘額，則 `MakeWithdrawal` 方法會擲回例外狀況：</span><span class="sxs-lookup"><span data-stu-id="2900e-197">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="2900e-198">[`throw`](../../language-reference/keywords/throw.md) 陳述式會**擲回**例外狀況。</span><span class="sxs-lookup"><span data-stu-id="2900e-198">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="2900e-199">目前區塊的執行會結束，而且控制權會移轉給呼叫堆疊中找到最初相符的 `catch` 區塊。</span><span class="sxs-lookup"><span data-stu-id="2900e-199">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="2900e-200">您會在稍後新增 `catch` 區塊來測試此程式碼。</span><span class="sxs-lookup"><span data-stu-id="2900e-200">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="2900e-201">應該對建構函式進行一個變更來使它會新增初始交易，而不是直接更新餘額。</span><span class="sxs-lookup"><span data-stu-id="2900e-201">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="2900e-202">由於您已撰寫 `MakeDeposit` 方法，請從建構函式呼叫它。</span><span class="sxs-lookup"><span data-stu-id="2900e-202">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="2900e-203">完成的建構函式應該看起來如下：</span><span class="sxs-lookup"><span data-stu-id="2900e-203">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="2900e-204"><xref:System.DateTime.Now?displayProperty=nameWithType> 是會傳回目前日期和時間的屬性。</span><span class="sxs-lookup"><span data-stu-id="2900e-204"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="2900e-205">透過在您的 `Main` 方法中新增一些存款和提款來測試此屬性：</span><span class="sxs-lookup"><span data-stu-id="2900e-205">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="2900e-206">接下來，透過建立具有負數餘額的帳戶，來測試是否能攔截到錯誤情況：</span><span class="sxs-lookup"><span data-stu-id="2900e-206">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="2900e-207">使用 [`try` 與 `catch` 陳述式](../../language-reference/keywords/try-catch.md)來標記可能會擲回例外狀況的程式碼區塊，並攔截您所預期的那些錯誤。</span><span class="sxs-lookup"><span data-stu-id="2900e-207">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="2900e-208">您可以使用同樣的技巧來測試會針對負數餘額擲回例外狀況的程式碼：</span><span class="sxs-lookup"><span data-stu-id="2900e-208">You can use the same technique to test the code that throws an exception for a negative balance:</span></span>

```csharp
// Test for a negative balance
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="2900e-209">儲存檔案並輸入 `dotnet run` 來嘗試它。</span><span class="sxs-lookup"><span data-stu-id="2900e-209">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="2900e-210">挑戰 - 記錄所有交易</span><span class="sxs-lookup"><span data-stu-id="2900e-210">Challenge - log all transactions</span></span>

<span data-ttu-id="2900e-211">若要完成此教學課程，您可以撰寫會針對交易記錄建立 `string` 的 `GetAccountHistory` 方法。</span><span class="sxs-lookup"><span data-stu-id="2900e-211">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="2900e-212">將此方法新增到 `BankAccount` 型別：</span><span class="sxs-lookup"><span data-stu-id="2900e-212">Add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="2900e-213">此方法使用 <xref:System.Text.StringBuilder> 類別來設定針對每個交易包含單一行之字串的格式。</span><span class="sxs-lookup"><span data-stu-id="2900e-213">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="2900e-214">您稍早已經在這些教學課程中看過字串格式設定的程式碼。</span><span class="sxs-lookup"><span data-stu-id="2900e-214">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="2900e-215">一個新的字元是 `\t`。</span><span class="sxs-lookup"><span data-stu-id="2900e-215">One new character is `\t`.</span></span> <span data-ttu-id="2900e-216">它會插入定位字元以設定輸出的格式。</span><span class="sxs-lookup"><span data-stu-id="2900e-216">That inserts a tab to format the output.</span></span>

<span data-ttu-id="2900e-217">新增下列行以在 **Program.cs** 中測試它：</span><span class="sxs-lookup"><span data-stu-id="2900e-217">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="2900e-218">輸入 `dotnet run` 來查看結果。</span><span class="sxs-lookup"><span data-stu-id="2900e-218">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2900e-219">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2900e-219">Next Steps</span></span>

<span data-ttu-id="2900e-220">如果遇到問題，您可以在我們的 [GitHub 存放庫](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/) \(英文\) 中查看此教學課程的原始程式碼</span><span class="sxs-lookup"><span data-stu-id="2900e-220">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="2900e-221">恭喜，您已完成所有 C# 簡介教學課程。</span><span class="sxs-lookup"><span data-stu-id="2900e-221">Congratulations, you've finished all our introduction to C# tutorials.</span></span> <span data-ttu-id="2900e-222">如果您想要學習更多，請嘗試更多[教學課程](../index.md)</span><span class="sxs-lookup"><span data-stu-id="2900e-222">If you're eager to learn more, try more of our [tutorials](../index.md)</span></span>
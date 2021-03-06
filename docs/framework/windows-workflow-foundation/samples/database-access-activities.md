---
title: 資料庫存取活動
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: 5a7c6fa6664acee8000c100513b2cc955ffa3392
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622460"
---
# <a name="database-access-activities"></a>資料庫存取活動
資料庫存取活動可讓您存取工作流程內的資料庫。 這些活動可讓您存取資料庫以擷取或修改資訊以及使用[ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081)來存取資料庫。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。
>
>  `<InstallDrive>:\WF_WCF_Samples`
>
>  如果此目錄不存在，請移至 （下載頁面） 以下載所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]範例。 此範例位於下列目錄。
>
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a>資料庫活動
 下列各節詳細說明此範例中包含的活動清單。

## <a name="dbupdate"></a>DbUpdate
 執行 SQL 查詢，該查詢會產生資料庫修改 (插入、更新、刪除和其他修改)。

 這個類別會以非同步方式執行其工作 (它衍生自 <xref:System.Activities.AsyncCodeActivity> 並且使用其非同步功能)。

 透過設定提供者非變異名稱 (`ProviderName`) 和連接字串 (`ConnectionString`)，或僅使用來自應用程式組態檔的連接字串組態名稱 (`ConfigFileSectionName`)，即可設定連接資訊。

 要執行的查詢是在其 `Sql` 屬性中設定，而參數是透過 `Parameters` 集合傳遞。

 在 `DbUpdate` 執行之後，受影響的記錄數目會在 `AffectedRecords` 屬性中傳回。

```
Public class DbUpdate: AsyncCodeActivity
{
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [DependsOn("Parameters")]
    public OutArgument<int> AffectedRecords { get; set; }
}
```

|引數|描述|
|-|-|
|ProviderName|ADO.NET 提供者的非變異名稱。 如果設定這個引數，則同樣必須設定 `ConnectionString`。|
|ConnectionString|連接至資料庫的連接字串。 如果設定這個引數，則同樣必須設定 `ProviderName`。|
|ConfigName|儲存連接資訊之組態檔區段的名稱。 如果設定這個引數，則不需要 `ProviderName` 和 `ConnectionString`。|
|CommandType|要執行之 <xref:System.Data.Common.DbCommand> 的型別。|
|Sql|要執行的 SQL 命令。|
|參數|SQL 查詢的參數集合。|
|AffectedRecords|受上一次作業影響的記錄數目。|

## <a name="dbqueryscalar"></a>DbQueryScalar
 執行從資料庫擷取單一值的查詢。

 這個類別會以非同步方式執行其工作 (它衍生自 <xref:System.Activities.AsyncCodeActivity%601> 並且使用其非同步功能)。

 透過設定提供者非變異名稱 (`ProviderName`) 和連接字串 (`ConnectionString`)，或僅使用來自應用程式組態檔的連接字串組態名稱 (`ConfigFileSectionName`)，即可設定連接資訊。

 要執行的查詢是在其 `Sql` 屬性中設定，而參數是透過 `Parameters` 集合傳遞。

 之後`DbQueryScalar`會執行，會傳回純量中`Result out`引數 (型別的`TResult`，也就是在基底類別中定義<xref:System.Activities.AsyncCodeActivity%601>)。

```
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|引數|描述|
|-|-|
|ProviderName|ADO.NET 提供者的非變異名稱。 如果設定這個引數，則同樣必須設定 `ConnectionString`。|
|ConnectionString|連接至資料庫的連接字串。 如果設定這個引數，則同樣必須設定 `ProviderName`。|
|ConfigName|儲存連接資訊之組態檔區段的名稱。 如果設定這個引數，則不需要 `ProviderName` 和 `ConnectionString`。|
|CommandType|要執行之 <xref:System.Data.Common.DbCommand> 的型別。|
|Sql|要執行的 SQL 命令。|
|參數|SQL 查詢的參數集合。|
|結果|查詢執行之後取得的純量。 這個引數的型別為 `TResult`。|

## <a name="dbquery"></a>DbQuery
 執行擷取物件清單的查詢。 執行查詢之後，會執行對應的函式 (它可以是<xref:System.Func%601> < `DbDataReader`， `TResult`> 或有<xref:System.Activities.ActivityFunc%601> < `DbDataReader`， `TResult`>)。 這個對應的函式會取得 `DbDataReader` 中的記錄，並且將它對應至要傳回的物件。

 透過設定提供者非變異名稱 (`ProviderName`) 和連接字串 (`ConnectionString`)，或僅使用來自應用程式組態檔的連接字串組態名稱 (`ConfigFileSectionName`)，即可設定連接資訊。

 要執行的查詢是在其 `Sql` 屬性中設定，而參數是透過 `Parameters` 集合傳遞。

 SQL 查詢的結果會使用 `DbDataReader` 擷取。 活動會逐一查看 `DbDataReader`，並且將 `DbDataReader` 中的資料列對應至 `TResult` 的執行個體。 使用者`DbQuery`必須提供對應程式碼，可在兩種方式： 使用<xref:System.Func%601> < `DbDataReader`， `TResult`> 或<xref:System.Activities.ActivityFunc%601> < `DbDataReader`， `TResult`>。 在第一個案例中，對應會在單一執行 Pulse 中完成。 因此這種方式速度較快，但是無法序列化為 XAML。 在第二個案例中，對應是在多次 Pulse 中執行。 因此，這種方式的速度較慢，但是可以序列化為 XAML，並且以宣告方式編寫 (任何存在的活動都可以參與對應)。

```
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [OverloadGroup("DirectMapping")]
    [DefaultValue(null)]
    public Func<DbDataReader, TResult> Mapper { get; set; }

    [OverloadGroup("MultiplePulseMapping")]
    [DefaultValue(null)]
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }
}
```

|引數|描述|
|-|-|
|ProviderName|ADO.NET 提供者的非變異名稱。 如果設定這個引數，則同樣必須設定 `ConnectionString`。|
|ConnectionString|連接至資料庫的連接字串。 如果設定這個引數，則同樣必須設定 `ProviderName`。|
|ConfigName|儲存連接資訊之組態檔區段的名稱。 如果設定這個引數，則不需要 `ProviderName` 和 `ConnectionString`。|
|CommandType|要執行之 <xref:System.Data.Common.DbCommand> 的型別。|
|Sql|要執行的 SQL 命令。|
|參數|SQL 查詢的參數集合。|
|Mapper|對應函式 (<xref:System.Func%601><`DbDataReader`， `TResult`>) 會採用記錄`DataReader`執行查詢而取得，並傳回型別的物件的執行個體`TResult`加入`Result`集合。<br /><br /> 在此案例中，對應是在單一執行 Pulse 中完成，但是無法使用設計工具以宣告方式邊寫。|
|MapperFunc|對應函式 (<xref:System.Activities.ActivityFunc%601><`DbDataReader`， `TResult`>) 會採用記錄`DataReader`執行查詢而取得，並傳回型別的物件的執行個體`TResult`加入`Result`集合。<br /><br /> 在此案例中，對應會在多個執行 Pulse 中完成。 此函式可以序列化為 XAML，並且以宣告方式編寫 (任何存在的活動都可以參與對應)。|
|結果|物件清單，該清單是執行查詢以及針對 `DataReader` 中的每項記錄執行對應函式而取得。|

## <a name="dbquerydataset"></a>DbQueryDataSet
 執行傳回 <xref:System.Data.DataSet> 的查詢。 這個類別會以非同步方式執行其工作。 它衍生自<xref:System.Activities.AsyncCodeActivity> < `TResult`> 並且使用其非同步功能。

 透過設定提供者非變異名稱 (`ProviderName`) 和連接字串 (`ConnectionString`)，或僅使用來自應用程式組態檔的連接字串組態名稱 (`ConfigFileSectionName`)，即可設定連接資訊。

 要執行的查詢是在其 `Sql` 屬性中設定，而參數是透過 `Parameters` 集合傳遞。

 之後`DbQueryDataSet`會執行`DataSet`會傳回`Result out`引數 (型別的`TResult`，也就是基底類別中定義<xref:System.Activities.AsyncCodeActivity%601>)。

```
public class DbQueryDataSet : AsyncCodeActivity<DataSet>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|引數|描述|
|-|-|
|ProviderName|ADO.NET 提供者的非變異名稱。 如果設定這個引數，則同樣必須設定 `ConnectionString`。|
|ConnectionString|連接至資料庫的連接字串。 如果設定這個引數，則同樣必須設定 `ProviderName`。|
|ConfigName|儲存連接資訊之組態檔區段的名稱。 如果設定這個引數，則不需要 `ProviderName` 和 `ConnectionString`。|
|CommandType|要執行之 <xref:System.Data.Common.DbCommand> 的型別。|
|Sql|要執行的 SQL 命令。|
|參數|SQL 查詢的參數集合。|
|結果|查詢執行之後取得的 <xref:System.Data.DataSet>。|

## <a name="configuring-connection-information"></a>設定連接資訊
 所有 DbActivities 會共用相同的組態參數。 您可以透過兩種方式加以設定：

- `ConnectionString + InvariantName`：設定 ADO.NET 提供者非變異名稱和連接字串。

    ```
    Activity dbSelectCount = new DbQueryScalar<DateTime>()
    {
        ProviderName = "System.Data.SqlClient",
        ConnectionString = @"Data Source=.\SQLExpress;
                             Initial Catalog=DbActivitiesSample;
                             Integrated Security=True",
        Sql = "SELECT GetDate()"
    };
    ```

- `ConfigName`：設定包含連接資訊的組態區段名稱。

    ```xml
    <connectionStrings>
        <add name="DbActivitiesSample"
             providerName="System.Data.SqlClient"
             connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
      </connectionStrings>
    ```

- 在活動中：

    ```
    Activity dbSelectCount = new DbQueryScalar<int>()
    {
        ConfigName = "DbActivitiesSample",
        Sql = "SELECT COUNT(*) FROM Roles"
    };
    ```

## <a name="running-this-sample"></a>執行這個範例

### <a name="setup-instructions"></a>安裝指示
 這個範例會使用資料庫。 範例中提供 set-up 和 load 指令碼 (Setup.cmd)。 您必須使用命令提示字元執行該檔案。

 Setup.cmd 指令碼會叫用 CreateDb.sql 指令碼檔，該檔案中包含的 SQL 命令會執行下列操作：

- 建立名為 DbActivitiesSample 的資料庫。

- 建立 Roles 資料表。

- 建立 Employees 資料表。

- 將三個記錄插入至 Roles 資料表。

- 將十二個記錄插入至 Employees 資料表。

##### <a name="to-run-setupcmd"></a>若要執行 Setup.cmd

1. 開啟命令提示字元。

2. 移至 DbActivities 範例資料夾。

3. 輸入"setup.cmd"，然後按 ENTER。

    > [!NOTE]
    >  Setup.cmd 會嘗試在本機電腦 SqlExpress 執行個體中安裝範例。 如果您想要將它安裝到其他 SQL Server 執行個體中，請使用新的執行個體名稱編輯 Setup.cmd。

##### <a name="to-uninstall-the-sample-database"></a>若要解除安裝範例資料庫

1. 在命令提示字元中從相同資料夾執行 Cleanup.cmd。

##### <a name="to-run-the-sample"></a>若要執行範例

1. 在 Visual Studio 2010 中開啟方案

2. 若要編譯方案，請按下 CTRL+SHIFT+B。

3. 若要執行範例但不進行偵錯，請按 CTRL+F5。

> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 範例](https://go.microsoft.com/fwlink/?LinkId=150780)以下載所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]範例。 此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

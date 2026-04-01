---
date: 2026-03-08
description: 學習如何使用 Aspose.Tasks for .NET 匯入專案檔案，包括如何指定檔案編碼以及高效載入 Microsoft Project
  檔案。
linktitle: Options for Loading in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 匯入專案檔案 – Aspose.Tasks 載入選項
url: /zh-hant/net/advanced-concepts/loading-options/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 匯入專案檔案 – Aspose.Tasks 載入選項

## 簡介

Aspose.Tasks for .NET 讓您輕鬆 **匯入專案檔案** 資料，支援 Microsoft Project、Primavera 以及其他格式。無論您需要讀取受密碼保護的檔案、設定自訂編碼，或處理解析錯誤，該函式庫皆透過載入選項提供精細的控制。在本教學中，我們將逐步說明最常見的情境，讓您能自信地 **載入 Microsoft Project 檔案** 物件於 .NET 應用程式中。

## 快速解答
- **什麼是匯入專案檔案的主要方式？** 使用帶有 `LoadOptions` 實例的 `Project` 建構函式。  
- **我可以開啟受密碼保護的檔案嗎？** 可以——在 `LoadOptions` 上設定 `Password` 屬性。  
- **如何指定檔案編碼？** 將 `Encoding` 物件指派給 `LoadOptions.Encoding`。  
- **錯誤處理可以自訂嗎？** 當然可以——提供委派給 `LoadOptions.ErrorHandler`。  
- **這些選項能用於 Primavera 檔案嗎？** 可以，透過 `LoadOptions` 內的 `PrimaveraReadOptions`。

## 先決條件

在深入之前，請確保您已具備以下條件：

1. **Visual Studio**（或任何您偏好的 .NET IDE）。  
2. **Aspose.Tasks for .NET** – 從 [網站](https://releases.aspose.com/tasks/net/) 下載。  
3. 具備 **C#** 語法與專案結構的基本概念。

現在環境已就緒，讓我們匯入所需的命名空間。

## 匯入命名空間

在您的 C# 專案中，加入以下 `using` 陳述式，使 API 類別可供使用：

```csharp
using Aspose.Tasks;
using System.Text;
using System.Threading;
```

## 如何使用載入選項匯入專案檔案

以下提供四個實用範例，涵蓋最常見的載入情境。

### 步驟 1：載入受密碼保護的專案

```csharp
public void WorkWithLoadOptionsAndPassword()
{
    // Initialize FileStream to load the project file
    using (var stream = new FileStream(DataDir + "PasswordProtectedProject.mpp", FileMode.Open))
    {
        // Create LoadOptions instance
        var options = new LoadOptions
        {
            Password = "password" // Set the password
        };

        // Load the project with specified options
        var project = new Project(stream, options);

        // Display project name
        Console.WriteLine(project.Get(Prj.Name));
    }
}
```

### 步驟 2：載入具有自訂選項的 Primavera 專案

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptions()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions()
    {
        ProjectUid = 3882, // Set the Project UID
        UndefinedConstraintHandlingBehavior = UndefinedConstraintHandlingBehavior.None,
        PreserveUids = true
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Load the Primavera project with specified options
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Display project name
    Console.WriteLine("Project Name: " + project.Get(Prj.Name));

    // Perform further operations with the loaded project
}
```

### 步驟 3：在匯入 XER 檔案時 **指定檔案編碼**

```csharp
public void SpecifyFileEncoding()
{
    // Create LoadOptions instance
    LoadOptions lo = new LoadOptions();

    // Specify encoding when opening a project from Primavera XER file
    lo.Encoding = Encoding.GetEncoding(1251);

    // Load the project with specified encoding
    var project = new Project("encoding1251.xer", lo);

    // Perform further operations with the loaded project
}
```

### 步驟 4：載入具有自訂錯誤處理的 Primavera 專案

```csharp
public void WorkWithLoadOptionsAndPrimaveraOptionsAndErrorHandler()
{
    // Create LoadOptions instance
    var loadOptions = new LoadOptions();

    // Configure Primavera reading options
    var primaveraOptions = new PrimaveraReadOptions
    {
        ProjectUid = 3882 // Set the Project UID
    };

    // Set Primavera reading options
    loadOptions.PrimaveraReadOptions = primaveraOptions;

    // Set custom error handling
    loadOptions.ErrorHandler = CustomDurationHandlerForFile;

    // Load the Primavera project with specified options and error handling
    var project = new Project(DataDir + "PrimaveraProject.xml", loadOptions);

    // Perform further operations with the loaded project
}

// Custom error handler method
private static object CustomDurationHandlerForFile(object sender, ParseErrorArgs args)
{
    // Implement custom error handling logic
}
```

依照上述步驟，您即可精確 **匯入專案檔案** 資料，依需求自訂載入流程，並確保應用程式的穩健性。

## 常見問題與技巧

- **密碼錯誤** – `Password` 屬性會拋出例外；載入前請確認憑證。  
- **不支援的編碼** – 確認您指定的代碼頁在目標機器上存在（例如 `Encoding.GetEncoding(1251)` 可用於西里爾文）。  
- **缺少 Primavera 選項** – 若需保留工作項目 UID，請設定 `PreserveUids = true`；否則可能出現重複 ID。  
- **錯誤處理程式回傳 null** – 回傳 `null` 會告訴解析器跳過有問題的元素；可依需求自行客製化。

## 常見問與答

**Q: Aspose.Tasks for .NET 是否相容於所有版本的 Microsoft Project？**  
A: 是的，它支援廣泛的 Microsoft Project 版本，您可以 **載入 Microsoft Project 檔案** 格式，從舊版 MPP 檔案到最新格式皆可。

**Q: 我可以將 Aspose.Tasks for .NET 與其他第三方函式庫整合嗎？**  
A: 當然可以。此函式庫可與其他 .NET 套件無縫合作，讓您能結合報表、使用者介面或資料存取框架。

**Q: Aspose.Tasks for .NET 是否提供文件與支援資源？**  
A: 有，您可參考完整的 [文件](https://reference.aspose.com/tasks/net/)，並透過 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 獲得支援。

**Q: Aspose.Tasks for .NET 有哪些授權方案？**  
A: 有，您可在 [Aspose.Tasks 官方網站](https://purchase.aspose.com/buy) 探索各種授權選項，包括免費試用與臨時授權。

**Q: Aspose.Tasks for .NET 的更新與新功能發布頻率為何？**  
A: Aspose.Tasks 定期推出更新，新增功能、提升效能，並確保與最新的 Microsoft Project 版本相容。

---

**最後更新：** 2026-03-08  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
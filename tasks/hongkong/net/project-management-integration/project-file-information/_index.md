---
title: 在 Aspose.Tasks 中檢索 MS 專案文件信息
linktitle: 在 Aspose.Tasks 中檢索項目文件資訊
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 擷取 Microsoft Project 檔案資訊。帶有程式碼範例的分步指南。
weight: 19
url: /zh-hant/net/project-management-integration/project-file-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中檢索 MS 專案文件信息

## 介紹
歡迎閱讀我們使用 Aspose.Tasks for .NET 擷取 Microsoft Project 檔案資訊的逐步指南。 Aspose.Tasks 是一個功能強大的函式庫，可讓 .NET 開發人員以程式設計方式處理 Microsoft Project 文件，從而實現讀取、寫入和操作項目資料等任務。
## 先決條件
在我們深入學習本教程之前，請確保您符合以下先決條件：
1. C# 和 .NET 的基本知識：本教學假設您對 C# 程式語言和 .NET 框架有基本的了解。
2. Visual Studio：安裝 Visual Studio 或任何其他與 .NET 開發相容的 IDE。
3.  Aspose.Tasks for .NET 函式庫：下載並安裝 Aspose.Tasks for .NET 函式庫。你可以找到下載鏈接[這裡](https://releases.aspose.com/tasks/net/).
4. Microsoft Project 檔案：準備好 Microsoft Project 檔案（本例為 XML 格式）以供測試之用。

## 導入命名空間
首先，您需要將必要的命名空間匯入到您的 C# 專案中以使用 Aspose.Tasks：
## 步驟1：導入Aspose.Tasks命名空間
```csharp
using Aspose.Tasks;
using System;

```
## 檢索 MS 專案文件信息
現在，讓我們將提供的範例程式碼分解為多個步驟：
## 步驟二：設定文檔目錄
```csharp
//文檔目錄的路徑。
string dataDir = "Your Document Directory";
```
代替`"Your Document Directory"`包含 MS Project 檔案的目錄路徑。
## 步驟 3：檢索專案文件信息
```csharp
var info = Project.GetProjectFileInfo(dataDir + "Project.xml");
```
此行代碼會擷取有關指定項目文件的資訊。代替`"Project.xml"`與您的 MS Project 檔案的名稱。
## 第四步：顯示項目訊息
```csharp
Console.WriteLine("CanRead: " + info.CanRead);
Console.WriteLine("ProjectApplicationInfo: " + info.ProjectApplicationInfo);
Console.WriteLine("ProjectFileFormat: " + info.ProjectFileFormat);
```
這些程式碼行顯示有關 MS Project 檔案的各種信息，例如其可讀性、應用程式資訊和檔案格式。

## 結論
在本教學中，我們學習如何使用 Aspose.Tasks for .NET 擷取 Microsoft Project 檔案資訊。透過執行這些簡單的步驟，您可以將此功能無縫整合到您的 .NET 應用程式中，使您能夠有效地使用 MS Project 檔案。
## 常見問題解答
### Aspose.Tasks 可以處理不同版本的 Microsoft Project 檔案嗎？
是的，Aspose.Tasks 支援各種版本的 Microsoft Project 文件，包括 MPP 和 XML 格式。
### Aspose.Tasks 與 .NET Core 相容嗎？
是的，Aspose.Tasks 與 .NET Framework 和 .NET Core 相容。
### 我可以使用 Aspose.Tasks 操作項目資料嗎？
當然，Aspose.Tasks 提供了以程式設計方式讀取、寫入和操作項目資料的廣泛功能。
### Aspose.Tasks 是否有免費試用版？
是的，您可以免費試用 Aspose.Tasks[這裡](https://releases.aspose.com/).
### 我可以在哪裡獲得 Aspose.Tasks 的支援？
您可以透過以下方式獲得對 Aspose.Tasks 的支持[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).## 完整原始碼
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

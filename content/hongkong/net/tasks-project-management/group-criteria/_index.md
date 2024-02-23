---
title: 在 Aspose.Tasks 中操作 MS 專案組標準
linktitle: Aspose.Tasks 中的群組標準
second_title: Aspose.Tasks .NET API
description: 探索如何使用 Aspose.Tasks 在 .NET 中以程式設計方式操作 MS Project 檔案。檢索任務組和標準資訊逐步範例。
type: docs
weight: 27
url: /zh-hant/net/tasks-project-management/group-criteria/
---
## 介紹
Aspose.Tasks for .NET 是一個功能強大的 API，有助於在 .NET 應用程式中處理 Microsoft Project 檔案。無論您是在開發專案管理軟體還是需要以程式設計方式操作專案數據，Aspose.Tasks 都提供了一套全面的功能來滿足您的需求。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
### 1. C#和.NET Framework知識
熟悉 C# 程式語言和 .NET Framework 對於理解和實作本教程中提供的範例至關重要。
### 2.安裝Aspose.Tasks for .NET
確保您的開發環境中安裝了 Aspose.Tasks for .NET。您可以從以下位置下載該程式庫[這裡](https://releases.aspose.com/tasks/net/)並按照提供的安裝說明進行操作。
### 3.整合開發環境（IDE）
在系統上安裝 Visual Studio 等 IDE，用於編寫和執行 C# 程式碼。

## 導入命名空間
首先，在 C# 程式碼中導入必要的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 第 1 步：載入 Microsoft Project 文件
首先，指定 Microsoft Project 檔案的路徑：
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
代替`"Your Document Directory"`與您的專案文件的路徑。
## 第 2 步：檢索任務組信息
接下來，檢索有關專案中任務組的資訊：
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
此程式碼片段列印任務組的總數，檢索第二個任務組、其名稱以及它所保存的條件的數量。
## 步驟 3：檢索任務組的標準訊息
現在，讓我們深入研究任務組內特定標準的詳細資訊：
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
此段顯示標準的各種屬性，例如其索引、欄位、分組資訊、儲存格顏色、字體顏色、群組間隔和起點。
## 步驟 4： 檢索 Criterion 的字體訊息
最後，取得標準的與字體相關的詳細資訊：
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
此步驟列印出字型名稱、大小、樣式以及標準是否按升序或降序排序。

## 結論
在本教程中，我們探討如何使用 Aspose.Tasks for .NET 從 Microsoft Project 檔案中擷取任務群組和條件的資訊。透過遵循逐步指南，您可以在 .NET 應用程式中以程式設計方式有效地處理專案資料。
## 常見問題解答
### Aspose.Tasks 可以處理大型 Microsoft Project 檔案嗎？
Aspose.Tasks 經過最佳化，可有效處理大型專案文件，確保高效能和可靠性。
### Aspose.Tasks 是否與所有版本的 Microsoft Project 相容？
是的，Aspose.Tasks 支援各種版本的 Microsoft Project，確保不同檔案格式之間的相容性。
### 我可以使用 Aspose.Tasks 操作項目資料嗎？
當然，Aspose.Tasks 提供了廣泛的功能來操作專案數據，包括任務、資源、日曆等。
### Aspose.Tasks 是否提供不同 .NET 平台的支援？
是的，Aspose.Tasks 支援多種 .NET 平台，包括 .NET Framework、.NET Core 和 .NET Standard。
### 是否有 Aspose.Tasks 社群論壇可供我尋求協助？
是的，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)提出問題、分享知識、與其他使用者協作。
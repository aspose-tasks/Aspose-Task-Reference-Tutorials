---
title: 在 Aspose.Tasks for .NET 中設定 MS Project XLSX 選項
linktitle: 在 Aspose.Tasks 中配置 XLSX 選項
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中設定 MS Project XLSX 選項。輕鬆自訂列、編碼等。
type: docs
weight: 11
url: /zh-hant/net/file-format-options/configuring-xlsx-options/
---
## 介紹
Microsoft Project (MS Project) 是一個強大的專案管理工具，Aspose.Tasks for .NET 提供無縫集成，以便以程式設計方式處理 MS Project 檔案。在本教學中，我們將逐步介紹使用 Aspose.Tasks for .NET 設定 MS Project XLSX 選項的過程。
## 先決條件
在我們開始之前，請確保您具備以下條件：
### 1. Aspose.Tasks for .NET 安裝
確保您的開發環境中安裝了 Aspose.Tasks for .NET。如果沒有，您可以從以下位置下載[Aspose.Tasks for .NET 下載頁面](https://releases.aspose.com/tasks/net/).
### 2. 對 C# 和 .NET Framework 的基本了解
需要熟悉 C# 程式語言和 .NET 框架才能學習本教學。
### 3.微軟專案文件
準備好要設定並另存為 XLSX 檔案的 Microsoft Project 檔案 (MPP)。

## 導入命名空間
首先，導入必要的命名空間：
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## 第 1 步：載入項目
```csharp
var project = new Project("YourProjectFile.mpp");
```
載入您要設定的 Microsoft Project 檔案。
## 第 2 步：定義 XlsxOptions
```csharp
var options = new XlsxOptions();
```
建立一個實例`XlsxOptions`配置儲存為 XLSX 的設定。
## 第 3 步：新增甘特圖列
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
將所需的甘特圖列新增至選項。
## 步驟 4：新增資源視圖列
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
在選項中包含資源視圖所需的欄位。
## 第 5 步：新增作業檢視列
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
在選項中為分配視圖新增所需的列。
## 第6步：設定編碼
```csharp
options.Encoding = Encoding.Unicode;
```
設定輸出檔案的編碼。
## 第 7 步：將專案另存為 XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
將具有配置選項的項目儲存為 XLSX 檔案。

## 結論
在本教學中，我們學習如何使用 Aspose.Tasks for .NET 設定 MS Project XLSX 選項。透過執行以下步驟，您可以根據您的要求自訂輸出格式，從而增強專案管理工作流程的靈活性和可用性。
## 常見問題解答

### Q：我可以分別為甘特圖、資源視圖和作業視圖配置不同的欄位嗎？

答：是的，您可以使用 Aspose.Tasks for .NET 為每個視圖獨立自訂列。

### Q：購買 Aspose.Tasks for .NET 之前是否有試用版？

答：是的，您可以從以下網站下載免費試用版：[Aspose.Tasks for .NET 發佈頁面](https://releases.aspose.com/).

### Q：如果我在實施過程中遇到任何問題或疑問，如何獲得支援？

答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求社區和 Aspose 支援團隊的幫助。

### Q：我可以在非 Windows 平台上使用 Aspose.Tasks for .NET 產生 XLSX 檔嗎？

答：Aspose.Tasks for .NET 主要是為 Windows 平台設計的，但您可以探索其他平台的相容性選項。

### Q：是否有任何臨時許可證選項可用於測試目的？

答：是的，您可以從以下機構獲得臨時許可證：[Aspose.Tasks 臨時授權頁面](https://purchase.aspose.com/temporary-license/).
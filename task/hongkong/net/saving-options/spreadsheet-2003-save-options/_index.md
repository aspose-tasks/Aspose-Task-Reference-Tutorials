---
title: MS Project 與 Aspose.Tasks 的 Spreadsheet 2003 選項
linktitle: Spreadsheet 2003 Aspose.Tasks 的儲存選項
second_title: Aspose.Tasks .NET API
description: Master Spreadsheet 2003 使用 Aspose.Tasks for .NET 儲存 MS 專案選項。以程式設計方式無縫自訂和儲存 MS Project 檔案。
type: docs
weight: 19
url: /zh-hant/net/saving-options/spreadsheet-2003-save-options/
---
## 介紹
在本教程中，我們將深入研究如何利用 Aspose.Tasks for .NET 來利用 Spreadsheet 2003 Save MS Project Options。這個強大的工具允許在 .NET 環境中無縫操作和自訂 MS Project 檔案。讓我們逐步分解該過程。
## 先決條件
在開始本教學之前，請確保您符合以下先決條件：
1. 安裝 Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[下載連結](https://releases.aspose.com/tasks/net/).
2. 熟悉 C# 程式設計：要掌握本教程中討論的概念，需要對 C# 程式語言有基本的了解。

## 導入命名空間
首先將必要的命名空間匯入到您的 C# 專案中：
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
這些命名空間提供對使用 Spreadsheet 2003 格式儲存 MS Project 檔案和自訂視圖選項所需的功能的存取。
## 第 1 步：載入項目
首先，使用 Aspose.Tasks 載入 MS Project 檔案：
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
代替`"Your Document Directory"`與您的 MS Project 檔案所在的實際目錄路徑。
## 第 2 步：定義儲存選項
透過建立實例來定義 Spreadsheet 2003 儲存選項`Spreadsheet2003SaveOptions`：
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## 第 3 步：自訂檢視列
自訂甘特圖、資源視圖和作業視圖的視圖列：
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
這些步驟將自訂列新增至相應的視圖中，從而增強 MS Project 檔案的視覺化和分析功能。
## 第 4 步：儲存項目
最後，使用指定的選項儲存項目：
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
此命令以 Spreadsheet 2003 格式和自訂視圖列儲存修改後的項目。

## 結論
利用Aspose.Tasks for .NET，特別是Spreadsheet 2003 Save MS Project Options，使開發人員能夠以程式設計方式有效地管理和自訂MS Project 檔案。透過遵循本教程中概述的逐步指南，您可以將這些功能無縫整合到您的 .NET 應用程式中，從而提高工作效率和靈活性。

## 常見問題解答
### Q：Aspose.Tasks for .NET 可以在 Web 和桌面應用程式中使用嗎？
答：是的，Aspose.Tasks for .NET 可以無縫整合到 Web 和桌面應用程式中，提供跨平台的一致功能。
### Q：Aspose.Tasks for .NET 有試用版嗎？
答：是的，您可以從以下位置存取 Aspose.Tasks for .NET 的免費試用版：[網站](https://releases.aspose.com/)，讓您可以在購買前探索其功能。
### Q：使用 Aspose.Tasks for .NET 自訂視圖列有限制嗎？
答：Aspose.Tasks for .NET 為視圖列提供了廣泛的自訂選項，且限制極小。然而，複雜的定制可能需要對庫有深入的了解。
### Q：如果在使用 Aspose.Tasks for .NET 時遇到問題，我可以尋求協助嗎？
答：當然！您可以在 Aspose.Tasks 論壇上找到全面的支援和資源：[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15)，專家和社群成員可以幫助解決您可能面臨的任何問題或挑戰。
### Q：如何取得 Aspose.Tasks for .NET 的臨時授權？
答：您可以從 Aspose.Tasks for .NET 取得臨時許可證。[購買頁面](https://purchase.aspose.com/temporary-license/)，使您能夠評估庫的全部功能。
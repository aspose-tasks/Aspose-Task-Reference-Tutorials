---
title: 掌握 Aspose.Tasks 的 MS Project 保存選項
linktitle: Aspose.Tasks 的常規保存選項
second_title: Aspose.Tasks .NET API
description: 了解使用 Aspose.Tasks for .NET 有效地儲存 MS Project 檔案。輕鬆為您的專案自訂輸出選項。
weight: 17
url: /zh-hant/net/saving-options/general-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握 Aspose.Tasks 的 MS Project 保存選項

## 介紹
Aspose.Tasks for .NET 提供了以程式設計方式操作 Microsoft Project 檔案的強大功能。在本教程中，我們將深入研究使用 Aspose.Tasks 提供的各種選項來保存 MS Project 檔案的複雜性。具體來說，我們將重點放在 Aspose.Tasks 可用的一般保存選項，讓您可以根據您的特定要求自訂輸出。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. 安裝 Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[下載連結](https://releases.aspose.com/tasks/net/).
2. 對 .NET Framework 的基本了解：熟悉 .NET 程式設計概念是有益的。

## 導入命名空間
在深入程式碼之前，請確保導入必要的名稱空間：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## 第 1 步：載入專案文件
首先，您需要使用 Aspose.Tasks 載入 MS Project 檔案：
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## 第 2 步：定義儲存選項
根據您的要求定義儲存選項。在此範例中，我們使用`Spreadsheet2003SaveOptions`：
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## 第 3 步：自訂檢視列
您可以自訂視圖列，例如甘特圖、資源視圖和分配視圖。以下是向每個新增列的方法：
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## 第 4 步：使用選項儲存項目
最後，使用指定的選項儲存項目：
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 結論
使用 Aspose.Tasks for .NET 掌握一般的 MS Project 儲存選項，讓您能夠根據專案的需求有效地自訂輸出格式。
## 常見問題解答
### Q：Aspose.Tasks 是否與不同版本的 MS Project 檔案相容？
答：是的，Aspose.Tasks 支援各種版本的 MS Project 文件，確保不同環境之間的相容性。
### Q：我可以在購買前試用 Aspose.Tasks 嗎？
答：是的，您可以透過免費試用版探索 Aspose.Tasks[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到 Aspose.Tasks 的文檔？
答：詳細的文件可以找到[這裡](https://reference.aspose.com/tasks/net/)，提供有關使用 Aspose.Tasks 功能的全面指導。
### Q：如何取得 Aspose.Tasks 的臨時許可證？
答：臨時許可證可用於評估目的[這裡](https://purchase.aspose.com/temporary-license/).
### Q：我可以在哪裡尋求 Aspose.Tasks 相關查詢的支援？
答：您可以加入Aspose.Tasks社群論壇[這裡](https://forum.aspose.com/c/tasks/15)獲得專家和其他開發人員的協助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: 使用 Aspose.Tasks 自訂甘特圖列
linktitle: Aspose.Tasks 中的甘特圖列
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中自訂甘特圖列以有效顯示特定任務資訊。
weight: 21
url: /zh-hant/net/tasks-project-management/gantt-chart-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 自訂甘特圖列

## 介紹
甘特圖是專案管理中的基本工具，提供任務、時間表和資源的可視化表示。 Aspose.Tasks for .NET 提供了操作甘特圖的強大功能，包括自訂列以顯示特定任務資訊。在本教程中，我們將探索如何使用 Aspose.Tasks for .NET 處理甘特圖列。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. 安裝：Aspose.Tasks for .NET 安裝在您的系統上。如果沒有，請從以下位置下載並安裝[這裡](https://releases.aspose.com/tasks/net/).
2. .NET 開發環境：C# 和 .NET 架構的應用知識。
3. 範例專案文件：有一個範例 Microsoft Project 檔案（`.mpp`）方便進行實驗。如果沒有，可以在 MS Project 中建立一個簡單的專案並儲存。

## 導入命名空間
首先，您需要匯入必要的命名空間以使用 Aspose.Tasks for .NET：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 第 1 步：載入專案文件
使用載入專案文件`Project`Aspose.Tasks 提供的類別：
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## 步驟 2：定義甘特圖列
定義要在甘特圖中顯示的欄位。您可以指定內建欄位或建立自訂欄位：
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## 第 3 步：迭代列
迭代定義的列以存取其屬性並顯示資訊：
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## 步驟 4：將甘特圖儲存為 CSV
將具有已定義列的甘特圖儲存到 CSV 檔案：
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
透過執行這些步驟，您可以有效地使用 Aspose.Tasks for .NET 中的甘特圖列，從而允許您根據需要自訂和顯示任務資訊。

## 結論
掌握 Aspose.Tasks for .NET 中甘特圖列的操作為根據您的特定需求自訂專案管理視覺效果提供了無限的可能性。透過遵循本教程中概述的步驟，您可以有效地處理任務資訊並增強專案的清晰度和組織性。
## 常見問題解答
### Q：我可以在 Aspose.Tasks for .NET 中建立自訂列嗎？
答：是的，您可以根據您的專案需求定義自訂列來顯示特定的任務屬性。
### Q：Aspose.Tasks for .NET 是否與所有版本的 Microsoft Project 檔案相容？
答：Aspose.Tasks for .NET 支援各種版本的 Microsoft Project 文件，確保不同專案環境之間的相容性。
### Q：如何使用 Aspose.Tasks for .NET 處理複雜的專案結構？
答：Aspose.Tasks for .NET 提供全面的 API 和功能來管理複雜的專案結構，提供靈活性和可擴充性。
### Q：我可以加到甘特圖中的列數有限制嗎？
答：Aspose.Tasks for .NET 提供了廣泛的自訂選項，可讓您無限制地在甘特圖上新增大量欄位。
### Q：在哪裡可以找到 Aspose.Tasks for .NET 的其他支援和資源？
答：您可以瀏覽 Aspose.Tasks for .NET 提供的文件、社群論壇和支援管道，以獲得全面的資源和協助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

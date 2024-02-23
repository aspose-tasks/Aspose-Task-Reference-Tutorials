---
title: 使用 Aspose.Tasks 處理 MS 專案進度線
linktitle: 處理 Aspose.Tasks 中的進度線
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 操作 MS Project 檔案中的進度線，從而增強專案視覺化和管理。
type: docs
weight: 15
url: /zh-hant/net/project-management-integration/progress-lines/
---
## 介紹
Microsoft Project (MS Project) 是一個強大的專案管理工具，可讓使用者追蹤專案的各個方面。 MS Project 的一項重要功能是能夠視覺化進度線，這有助於利害關係人了解專案的狀態和軌跡。在本教程中，我們將探索如何使用 .NET 的 Aspose.Tasks 庫處理 MS Project 中的進度線。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. Visual Studio：安裝 Visual Studio 或任何其他首選的 .NET 開發環境。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[這裡](https://releases.aspose.com/tasks/net/).
3. C# 基礎：熟悉 C# 程式語言將會很有幫助。

## 導入命名空間
首先，讓我們導入必要的命名空間：
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
現在，讓我們分解處理進度線的每個步驟：
## 第 1 步：載入專案文件
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
在這裡，我們加載 MS Project 文件`Project2.mpp`並設定其狀態日期。
## 第 2 步：定義甘特圖視圖
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
我們將專案的視圖轉換為甘特圖視圖以進行進一步的操作。
## 第 3 步：定義進度線
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
我們初始化甘特圖視圖的進度線。
## 步驟 4：配置進度線設置
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
在這裡，我們為進度線設定各種屬性，例如線條顏色、圖案、字體等。
## 第 5 步：檢查進度線配置
```csharp
//輸出進度線設定
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
//輸出其他設定...
```
我們輸出配置的進度線設定以進行驗證。
## 第 6 步：儲存專案文件
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
最後，我們儲存修改後的帶有進度線的專案檔案。

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for .NET 處理 MS Project 進度線。透過執行這些步驟，您可以以程式設計方式有效地自訂和視覺化 MS Project 檔案中的進度線。
## 常見問題解答
### Q：我可以進一步自訂進度線的外觀嗎？
答：是的，您可以調整各種屬性，例如線條顏色、圖案和字體來滿足您的要求。
### Q：Aspose.Tasks 是否支援其他專案管理功能？
答：是的，Aspose.Tasks 為操作 MS Project 檔案的各個方面提供了廣泛的支持，包括任務、資源和日曆。
### Q：我可以將 Aspose.Tasks 與其他 .NET 函式庫整合嗎？
答：當然，Aspose.Tasks 旨在與其他 .NET 程式庫無縫集成，讓您進一步增強專案管理應用程式。
### Q：是否有 Aspose.Tasks 支援的社群論壇？
答：是的，您可以在 Aspose.Tasks 論壇上找到有用的資源並尋求協助。[這裡](https://forum.aspose.com/c/tasks/15).
### Q：Aspose.Tasks 是否提供用於評估目的的臨時許可證？
答：是的，您可以從以下位置取得臨時評估許可證：[這裡](https://purchase.aspose.com/temporary-license/).
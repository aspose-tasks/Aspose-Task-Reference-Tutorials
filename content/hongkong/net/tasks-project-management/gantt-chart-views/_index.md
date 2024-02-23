---
title: 掌握 Aspose.Tasks 中的甘特圖視圖
linktitle: Aspose.Tasks 中的甘特圖視圖
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 Microsoft Project 檔案中自訂甘特圖視圖。高效專案管理的逐步指南。
type: docs
weight: 22
url: /zh-hant/net/tasks-project-management/gantt-chart-views/
---
## 介紹
甘特圖是專案管理中用於視覺化任務、時間表和依賴關係的強大工具。 Aspose.Tasks for .NET 提供了在 Microsoft Project 檔案中處理甘特圖視圖的強大功能。在本教程中，我們將探索如何利用 Aspose.Tasks 操作甘特圖視圖、自訂其外觀並將其儲存為 PDF 檔案。
## 先決條件
在繼續之前，請確保您具備以下先決條件：
### 1.安裝Aspose.Tasks for .NET
請確定您已安裝 Aspose.Tasks for .NET。您可以從以下位置下載該程式庫[這裡](https://releases.aspose.com/tasks/net/)並按照文件中提供的安裝說明進行操作[這裡](https://reference.aspose.com/tasks/net/).
### 2. 微軟專案文件
準備 Microsoft Project 文件（`Project2.mpp`）您將使用它來處理甘特圖視圖。
### 3. C#和.NET Framework基礎知識
本教學假設您對 C# 程式語言和 .NET 框架有基本的了解。
## 導入命名空間
在開始在 Aspose.Tasks 中使用甘特圖視圖之前，您需要將必要的命名空間匯入到 C# 程式碼中。您可以這樣做：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

讓我們將提供的範例程式碼分解為多個步驟並詳細解釋每個步驟：
## 第 1 步：載入專案文件
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
此步驟涉及載入 Microsoft Project 檔案（`Project2.mpp` ）到一個實例`Project`班級。
## 第 2 步：設定狀態日期
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
在這裡，我們將專案的狀態日期設定為其開始日期。
## 第 3 步：訪問甘特圖視圖
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
我們從專案中存取甘特圖視圖。 Aspose.Tasks 允許存取甘特圖、網路圖和任務使用等視圖。
## 第 4 步：自訂甘特圖視圖
現在，讓我們自訂甘特圖視圖的各個方面：
### 設定欄舍入
```csharp
view.BarRounding = false;
```
這設定甘特圖上的條是否四捨五入到最近的一天。
### 設定條形尺寸
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
這決定了圖表中甘特條的高度。
### 隱藏捲軸
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
指定展開摘要任務時是否隱藏捲軸。
### 設定非工作時間顏色
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
定義甘特圖上非工作時間的顏色。
### 捲起甘特條
```csharp
view.RollUpGanttBars = true;
```
指定甘特圖上的條是否必須捲起。
### 顯示條形分割
```csharp
view.ShowBarSplits = true;
```
決定是否必須在甘特圖上顯示任務拆分。
### 展示圖紙
```csharp
view.ShowDrawings = true;
```
指定是否必須顯示甘特圖上的繪圖。
### 時間刻度大小百分比
```csharp
view.TimescaleSizePercentage = 10;
```
設定百分比以調整時間刻度層上單位之間的間距。
## 步驟 5：將甘特圖視圖另存為 PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
最後，我們將客製化的甘特圖視圖儲存為 PDF 檔案。
## 結論
在本教程中，我們學習如何在 Aspose.Tasks for .NET 中使用甘特圖視圖。透過遵循提供的步驟，您可以根據您的專案需求有效地操作和自訂甘特圖。
## 常見問題解答
### Q：我可以進一步自訂甘特圖條形的外觀嗎？
答：是的，Aspose.Tasks 提供了廣泛的選項來自訂甘特圖條的外觀，包括顏色、形狀和大小。
### Q：Aspose.Tasks 是否與不同版本的 Microsoft Project 檔案相容？
答：是的，Aspose.Tasks 支援各種版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。
### Q：我可以將甘特圖視圖匯出為 PDF 以外的格式嗎？
答：當然，Aspose.Tasks 支援將甘特圖視圖匯出為多種格式，包括 PNG、JPEG 和 XPS。
### Q：Aspose.Tasks 是否支援複雜的專案調度演算法？
答：是的，Aspose.Tasks 提供了先進的調度演算法來有效地處理複雜的專案調度。
### Q：是否有社群論壇可供我尋求協助或分享我使用 Aspose.Tasks 的經驗？
答： 是的，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)與其他用戶互動、提出問題並找到問題的解決方案。
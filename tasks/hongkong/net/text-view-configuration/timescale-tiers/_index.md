---
title: 在 Aspose.Tasks 中配置甘特圖時間刻度層
linktitle: 在 Aspose.Tasks 中配置時間刻度層
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 在甘特圖視圖中配置時間刻度層，以實現精確的專案時間軸視覺化。 #Aspose.Tasks #MS 項目
weight: 16
url: /zh-hant/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中配置甘特圖時間刻度層

## 介紹
在專案管理的動態環境中，有效的視覺化對於理解時間表和截止日期至關重要。 Aspose.Tasks for .NET 提供了強大的工具集，在本教程中，我們將探討如何配置時間刻度層以在甘特圖視圖中實現最佳表示。請按照這些逐步說明來增強您的專案視覺化。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
- C# 和 .NET 的基礎知識。
- 安裝了 .NET 函式庫的 Aspose.Tasks。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
- 為 .NET 應用程式開發而設定的開發環境。
## 導入命名空間
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
現在，讓我們分解所提供範例的每個步驟。
## 第 1 步：初始化項目並新增任務鏈接
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
在這裡，我們建立一個專案並在「任務 1」和「任務 2」之間建立任務連結。
## 第 2 步：配置甘特圖視圖
```csharp
var view = (GanttChartView)project.DefaultView;
```
存取甘特圖視圖進行自訂。
## 第 3 步：調整中間時間刻度層
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
自訂中間時間刻度層以顯示具有特定標籤和對齊方式的周。
## 步驟 4：新增頂級時間刻度層
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
新增頂部時間刻度層來表示月份。
## 第 5 步：自訂中間層日期
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
個性化月份標籤以獲得更好的視覺化效果。
## 第 6 步：設定專案時間表
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
定義專案時間表以控制總體時間表。
## 第 7 步：使用自訂時間刻度儲存項目
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
使用定義的時間刻度設定儲存項目。
## 結論
總之，在 Aspose.Tasks for .NET 中配置時間刻度層可以實現專案時間軸的客製化和視覺吸引力的表示。這些步驟使您能夠建立精確滿足您的專案管理需求的甘特圖視圖。
## 常見問題解答
### 我可以將 Aspose.Tasks 與其他 .NET 函式庫一起使用嗎？
是的，Aspose.Tasks 與其他 .NET 程式庫無縫集成，為您的開發堆疊提供靈活性。
### 臨時許可證是否可用於測試目的？
是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)進行評估。
### 甘特圖視圖是否有其他自訂選項？
當然，Aspose.Tasks 為甘特圖視圖提供了廣泛的自訂選項，以滿足不同的專案需求。
### 我可以以不同的格式渲染時間刻度嗎？
當然，您可以探索時間刻度表示的各種格式和樣式，以最適合您的專案環境。
### 是否有 Aspose.Tasks 支援的社群論壇？
是的，請訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持和討論。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

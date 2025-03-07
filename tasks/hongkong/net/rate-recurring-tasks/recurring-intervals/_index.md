---
title: Aspose.Tasks 中輕鬆的 MS 項目重複間隔
linktitle: 管理 Aspose.Tasks 中的重複間隔
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 輕鬆管理 MS Project 中的重複間隔。
weight: 12
url: /zh-hant/net/rate-recurring-tasks/recurring-intervals/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中輕鬆的 MS 項目重複間隔

## 介紹
您是否希望使用 Aspose.Tasks for .NET 在 Microsoft Project 檔案中有效管理重複間隔？這個全面的教學將逐步引導您完成整個過程，確保您可以輕鬆處理專案中的重複間隔。在深入學習本教學之前，我們先了解一些先決條件，以確保您已準備好開始使用。
## 先決條件
在繼續本教學之前，請確保您具備以下條件：
1. C# 程式設計知識：需要對 C# 程式語言及其語法有基本的了解。
2. 安裝了 Visual Studio：確保您的系統上安裝了 Visual Studio，用於編碼和編譯 .NET 應用程式。
3. Aspose.Tasks for .NET 函式庫：下載並安裝 Aspose.Tasks for .NET 函式庫。你可以從[這裡](https://releases.aspose.com/tasks/net/).

## 導入命名空間
首先匯入必要的命名空間以存取 Aspose.Tasks for .NET 函式庫提供的功能。
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
現在，讓我們將每個範例分解為多個步驟並詳細解釋它們。
## 第 1 步：初始化項目物件：
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
在這裡，我們初始化一個新的實例`Project`類，透過提供 Microsoft Project 檔案的路徑。
## 第 2 步：設定狀態日期：
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
此步驟將專案的狀態日期設定為其開始日期。
## 第 3 步：存取甘特圖視圖：
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
我們訪問專案的甘特圖視圖。
## 第 4 步：閱讀進度線：
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
此步驟從甘特圖視圖中擷取進度線的重複間隔。
## 步驟 5：顯示間隔資訊：
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
在這裡，我們顯示有關間隔、每週週數和每週天數的資訊。
## 第 6 步：重新定義重複間隔：
```csharp
var newInterval = new RecurringInterval();
```
我們建立一個新實例`RecurringInterval`重新定義重複間隔。
## 第 7 步：設定每月進度線：
```csharp
//按天設定每月進度線。
interval.MonthlyDay = true;
//設定每月進度線的天數。
interval.MonthlyDayDayNumber = 1;
//設定每月進度線的月份數。
interval.MonthlyDayMonthNumber = 1;
//按預先定義的第一天或最後一天設定進度線。
interval.MonthlyFirstLast = true;
//設定每月進度線的第一天或最後一天類型。
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
//設定進度線的月份數。
interval.MonthlyFirstLastMonthNumber = 1;
```
這些步驟根據指定的參數配置每月進度線。
## 第 8 步：更新進度線：
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
我們使用新定義的重複間隔來更新甘特圖視圖中的進度線。
## 第 9 步：將項目另存為 PDF：
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
最後，我們將更新後的重複間隔的項目儲存為 PDF 檔案。

## 結論
總之，透過此程式庫提供的全面功能，使用 Aspose.Tasks for .NET 管理 Microsoft Project 檔案中的重複間隔變得非常簡單。透過遵循本教程中概述的逐步指南，您可以有效地處理專案中的重複間隔，從而提高工作效率和組織性。
### 常見問題解答
### 我可以將 Aspose.Tasks for .NET 與其他程式語言一起使用嗎？
是的，Aspose.Tasks for .NET 可以與任何 .NET 支援的語言一起使用，例如 C# 和 VB.NET。
### Aspose.Tasks for .NET 有沒有試用版？
是的，您可以從以下位置下載免費試用版[這裡](https://releases.aspose.com/).
### 如何獲得 Aspose.Tasks for .NET 支援？
您可以從 Aspose.Tasks 論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).
### 我可以購買 Aspose.Tasks for .NET 的臨時授權嗎？
是的，您可以從以下位置購買臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以找到 Aspose.Tasks for .NET 的完整文件？
完整的文檔可以找到[這裡](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: 在 Aspose.Tasks 中自訂工作週
linktitle: Aspose.Tasks 中工作週的集合
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中自訂工作週。建立個人化專案日曆的逐步指南。現在下載！
type: docs
weight: 17
url: /zh-hant/net/time-recurrence-configuration/workweek-collection/
---
## 介紹
歡迎來到我們關於使用 Aspose.Tasks for .NET 建立自訂工作週的教學！在本逐步指南中，我們將引導您完成為專案中的日曆定義個人化工作週的過程。 Aspose.Tasks 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中有效地處理 Microsoft Project 文件。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. Visual Studio：確保您的電腦上安裝了 Visual Studio。
2.  Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks 函式庫。你可以找到下載鏈接[這裡](https://releases.aspose.com/tasks/net/).
3. C# 基礎知識：熟悉 C# 程式語言基礎。
## 導入命名空間
在您的 C# 專案中，確保匯入必要的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 第 1 步：建立專案和日曆
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## 第 2 步：定義自訂工作週
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## 第 3 步：設定工作日
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## 第 4 步：顯示工作週資訊
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
此綜合指南使您能夠使用 Aspose.Tasks for .NET 有效地建立和管理自訂工作週。
## 結論
總之，Aspose.Tasks for .NET 提供了一個強大的解決方案，用於處理具有自訂工作週的專案日曆。透過學習本教程，您已了解如何在專案中建立和顯示有關自訂工作週的資訊。
## 常見問題解答
### 我可以在一個專案中設定多個自訂工作週嗎？
是的，您可以將多個自訂工作週新增至專案行事曆。
### 如何修改現有的工作週？
使用提供的`WorkWeek`修改現有工作週的屬性和方法。
### Aspose.Tasks 與 .NET Core 相容嗎？
是的，Aspose.Tasks 支援 .NET Core。
### 我可以將具有自訂工作週的專案匯出為 Microsoft Project 檔案格式嗎？
當然，Aspose.Tasks 允許您以各種格式儲存項目，包括 Microsoft Project。
### 我可以在哪裡尋求 Aspose.Tasks 相關查詢的支援？
訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求任何支持或幫助。
---
title: Aspose.Tasks 中日曆異常的集合
linktitle: Aspose.Tasks 中日曆異常的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 有效處理 .NET 專案中的行事曆異常，確保準確的排程和資源管理。
type: docs
weight: 13
url: /zh-hant/net/calendar-scheduling/calendar-exception-collection/
---
## 介紹

在專案管理中，精確的調度對於成功至關重要。然而，由於假期、特殊事件或其他因素，現實場景通常需要偏離標準時間表。 Aspose.Tasks for .NET 提供了一個強大的解決方案，透過其行事曆異常收集功能來管理此類例外狀況。本教學將引導您逐步完成使用此功能的過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

1.  Aspose.Tasks for .NET：確保您已安裝程式庫。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
2. C#基礎知識：熟悉C#程式語言將有助於理解範例。
3. 開發環境：設定您首選的開發環境，例如 Visual Studio 或 JetBrains Rider。

## 導入命名空間

在開始使用 Aspose.Tasks for .NET 之前，您需要將所需的命名空間匯入到您的專案中。此步驟使您能夠存取管理日曆異常所需的類別和方法。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

現在，讓我們將提供的範例分解為多個步驟：

## 第 1 步：載入項目並檢索日曆

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

在此步驟中，我們載入專案文件並透過其 UID 檢索所需的日曆。

## 步驟 2：清除現有例外情況並設定標準日曆

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

此步驟從日曆中清除任何現有例外並將其設定為標準配置。

## 步驟 3：定義並新增工作時間例外

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

此步驟定義具有特定開始和結束日期的工作時間例外，以及這些日期內的工作時間，並將其新增至行事曆。

## 第 4 步：定義並新增非工作時間例外情況

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

//如果需要，請添加更多例外

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

此步驟定義非工作時間例外（例如假日），並將其新增至行事曆。

## 第 5 步：顯示日曆例外狀況

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

此步驟顯示新增的日曆例外及其詳細資訊。

## 第 6 步：刪除所有異常

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

最後，此步驟從日曆中刪除所有例外情況。

## 結論

管理日曆異常對於準確的專案安排至關重要。 Aspose.Tasks for .NET 透過提供一套全面的功能（包括日曆例外集合）來簡化此任務。透過遵循本教學中概述的步驟，您可以有效地處理專案中的各種調度方案。

## 常見問題解答

### Q1：我可以在一個行事曆中新增多個例外嗎？

 A1：是的，您可以使用以下命令為日曆新增多個例外：`AddRange`方法。

### Q2：如何處理經常出現的例外情況，例如每週假期？

A2：您可以以程式設計方式計算重複出現的異常，並使用自訂邏輯將它們新增至日曆中。

### Q3：是否可以從外部來源匯入行事曆例外？

A3：是的，您可以從資料庫或 CSV 檔案等外部來源讀取日曆例外，並將其整合到您的專案中。

### Q4：如果日曆中有重疊的例外情況會如何？

A4：Aspose.Tasks for .NET 可讓您根據專案需求定義優先順序或解決衝突來處理重疊例外狀況。

### Q5：例外情況下我可以自訂每天的工作時間嗎？

A5：是的，您可以在例外情況下為個別日期指定自訂工作時間，以滿足特定的日程安排需求。
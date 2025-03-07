---
title: Aspose.Tasks 中的每日日曆重複
linktitle: Aspose.Tasks 中的每日日曆重複
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中透過每日日曆重複建立重複任務。輕鬆提高專案管理效率。
weight: 25
url: /zh-hant/net/calendar-scheduling/daily-calendar-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的每日日曆重複

## 介紹

 Aspose.Tasks for .NET 提供了一組強大的工具，以程式設計方式管理任務和專案。其顯著功能之一是能夠有效處理日常日曆重複。在本教程中，我們將探討如何利用`DailyCalendarRepetition`類別以及其他相關類，根據指定的日曆建立每日重複的重複任務。

## 先決條件

在開始之前，請確保您已進行以下設定：

1. 安裝：確保您已安裝 Aspose.Tasks for .NET。如果沒有，您可以從以下位置下載[這裡](https://releases.aspose.com/tasks/net/).

2. 命名空間匯入：將必要的命名空間匯入到您的專案中：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## 第 1 步：初始化項目

首先，我們需要載入現有項目或建立一個新項目來使用：

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 第 2 步：定義日曆

接下來，我們建立一個持續時間為 24 小時的日曆並將其與專案關聯：

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## 步驟 3：設定重複任務參數

現在，讓我們為重複任務設定參數。我們定義它的名稱、持續時間、重複模式和範圍：

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## 步驟 4：設定任務日曆

將定義的日曆與任務關聯：

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## 第 5 步：將任務新增至項目

將具有定義參數的任務新增至專案：

```csharp
project.RootTask.Children.Add(parameters);
```

## 第 6 步：儲存項目

最後，儲存新增了重複任務的項目：

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

現在，您已經使用 Aspose.Tasks for .NET 成功建立了一個項目，其中的重複任務設定為基於 24 小時日曆每天重複！

## 結論

在本教學中，我們示範如何利用 Aspose.Tasks for .NET 有效地處理每日行事曆重複。透過執行這些步驟，您可以將重複任務無縫整合到您的專案中，從而提高生產力和組織性。

## 常見問題解答

### Q1：我可以自訂每次重複的持續時間嗎？

A1：是的，您可以根據自己的要求，透過修改程式碼中的參數來調整每次重複的持續時間。

### Q2：同一專案中的不同任務是否可以設定不同的行事曆？

A2：當然，Aspose.Tasks 允許您將特定的日曆分配給各個任務，從而提供日程安排的靈活性。

### Q3：Aspose.Tasks 是否支援除每日以外的其他重複模式？

A3：是的，Aspose.Tasks 提供了週、月、年等多種重複模式，滿足不同的專案需求。

### Q4：我可以視覺化使用 Aspose.Tasks 建立的重複任務嗎？

A4：當然，Aspose.Tasks 提供視覺化選項來幫助您有效地分析和追蹤重複任務。

### Q5：Aspose.Tasks 有試用版嗎？

 A5：是的，您可以免費試用 Aspose.Tasks[這裡](https://releases.aspose.com/)在購買之前探索其功能。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
date: 2026-04-13
description: 學習如何在 Aspose.Tasks for .NET 中刪除行事曆例外，並在管理 ASP.NET 行事曆排程時檢查例外日期。
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: 使用 Aspose.Tasks 刪除日曆例外
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 刪除行事曆例外
url: /zh-hant/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 刪除日曆例外與 Aspose.Tasks

## 簡介

在本教學中，您將學習如何 **刪除日曆例外**，以及如何在 Aspose.Tasks 中使用 .NET 框架管理其他日曆例外。日曆例外讓您能夠模擬假期、臨時關閉或任何正常工作時間變更的特殊期間。了解如何新增、查詢和移除這些例外對於精確的專案排程至關重要，尤其是在 **ASP.NET 日曆排程** 情境中。

## 快速解答
- **移除例外的主要方法是什麼？** 使用 `CalendarException` 物件的 `Delete()` 方法。  
- **哪個類別用於檢查日期是否在例外範圍內？** `CalendarException.CheckException()`——可用於 **檢查例外日期**。  
- **執行程式碼是否需要授權？** 是的，生產環境必須使用有效的 Aspose.Tasks 授權。  
- **我可以在同一個日曆中新增多個例外嗎？** 當然可以；`Exceptions` 集合支援多個條目。  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什麼是日曆例外？

**日曆例外** 代表與常規工作日曆的偏離——可視為一條規則，表示「在這些日期，工作時間不同或完全沒有」。在 Aspose.Tasks 中，每個例外都可以擁有自己的工作時間、重複模式以及指示該天是否為工作日的旗標。

## 為何在 ASP.NET 日曆排程中管理日曆例外？

- **準確的時間線：** 專案會自動遵守假期與特殊關閉，避免不切實際的截止日期。  
- **彈性：** 您可以定義每日、每週、每月或每年的模式，以符合現實商業日曆。  
- **自動化：** 以程式方式檢查例外日期，使您能在 ASP.NET 應用程式中構建動態排程邏輯。

## 先決條件

- 基本的 C# 程式設計知識。  
- Visual Studio（任何較新版本）。  
- 已在專案中加入 Aspose.Tasks for .NET 程式庫（透過 NuGet 或手動參考）。

## 匯入命名空間

首先，匯入您需要的命名空間：

```csharp
using Aspose.Tasks;
using System;
```

## 步驟 1：刪除日曆例外

移除不需要的例外相當簡單。以下程式碼會載入專案、選取第一個日曆、顯示基本資訊、刪除第一個例外，然後顯示更新後的計數。

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **專業提示：** 在呼叫 `Delete()` 之前，務必確認例外索引是否存在，以避免 `IndexOutOfRangeException`。

## 步驟 2：取得日曆例外的工作時間

如果需要檢查例外所定義的工作時段，請使用 `GetWorkingTime()`。此範例同時示範如何使用 `CheckException` **檢查例外日期**。

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## 步驟 3：定義日曆例外

以下是一個完整的操作流程，展示如何 **新增**、**檢查** 與 **移除** 日曆例外。請注意使用 `CheckException` 來 **檢查特定時刻的例外日期**。

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## 常見問題與技巧

| 問題 | 原因 | 解決方案 |
|-------|--------|----------|
| **刪除時的 `IndexOutOfRangeException`** | 嘗試刪除不存在的例外。 | 在呼叫 `Delete()` 前，確認 `calendar.Exceptions.Count` 大於索引。 |
| **工作時間不正確** | 未正確設定 `DayWorking` 或 `WorkingTimes`。 | 使用 `exception.WorkingTimes.Add(new WorkingTime(...))` 來定義明確的時間段。 |
| **例外未被識別** | `CheckException` 回傳 `false`，因為日期不在定義的範圍內。 | 再次確認 `FromDate`/`ToDate` 以及 `Type`（每日、每週等）。 |

## 常見問題

**Q: 我可以在單一日曆中新增多個例外嗎？**  
**A:** 是的，您可以根據需要新增任意數量的例外，以表示假期、維護窗口或任何特殊排程規則。

**Q: 我該如何 **檢查例外日期** 於特定日期？**  
**A:** 使用 `CalendarException` 實例的 `CheckException(DateTime date)` 方法。若提供的日期落在例外範圍內，會回傳 `true`。

**Q: 是否可以從日曆中移除已存在的例外？**  
**A:** 當然可以。存取 `Exceptions` 集合，然後呼叫 `Remove()` 或對特定的 `CalendarException` 物件使用 `Delete()`。

**Q: 支援哪些類型的日曆例外？**  
**A:** Aspose.Tasks 支援每日、每週、每月與每年例外類型，讓您能彈性地建模幾乎任何重複模式。

**Q: 我可以為特定例外日期自訂工作時間嗎？**  
**A:** 可以。建立例外後，將 `WorkingTime` 物件加入其 `WorkingTimes` 集合，以定義該日的開始與結束時間。

## 結論

我們已完整說明 **刪除日曆例外** 的全流程，從檢視現有例外、新增例外到檢查日期。精通這些技巧可確保您的專案排程遵循真實世界的日曆，使您的 ASP.NET 日曆排程實作更為穩健可靠。

---

**最後更新：** 2026-04-13  
**測試版本：** Aspose.Tasks for .NET (latest release)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
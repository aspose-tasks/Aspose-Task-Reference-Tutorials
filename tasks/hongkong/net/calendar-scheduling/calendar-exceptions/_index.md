---
title: 處理 Aspose.Tasks 中的日曆異常
linktitle: 處理 Aspose.Tasks 中的日曆異常
second_title: Aspose.Tasks .NET API
description: 透過逐步教學和範例，了解如何在 Aspose.Tasks for .NET 中管理行事曆異常。
weight: 12
url: /zh-hant/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 處理 Aspose.Tasks 中的日曆異常

## 介紹

在本教程中，我們將探討如何使用 .NET 框架在 Aspose.Tasks 中管理日曆例外狀況。日曆例外允許我們在專案日曆中定義特殊日期或時期，其中常規工作時間表會發生變化，例如假期或臨時關閉。我們將使用 Aspose.Tasks for .NET 逐步介紹處理行事曆例外狀況的各種方法。

## 先決條件

在我們開始之前，請確保您符合以下先決條件：
- C# 程式語言的基礎知識。
- Visual Studio 安裝在您的系統上。
- Aspose.Tasks for .NET 函式庫已新增至您的專案中。

## 導入命名空間

首先，讓我們為我們的專案導入必要的命名空間：

```csharp
using Aspose.Tasks;
using System;


```

## 步驟 1：刪除日曆例外

若要刪除行事曆例外，請依照下列步驟操作：

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    //顯示日曆資訊
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    //刪除第一個異常
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## 步驟2：取得日曆異常的工作時間

若要擷取日曆例外的工作時間，請依照下列步驟操作：

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    //顯示日曆和異常訊息
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    //獲取工作時間並顯示詳細信息
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

若要新增或刪除日曆例外，請依照下列步驟操作：

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    //建立新的日曆例外
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    //設定異常詳細資訊
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    //檢查日期是否異常
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    //將例外加入日曆中
    calendar.Exceptions.Add(exception);

    //刪除異常（如果存在）
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    //新增新的例外
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    //列印例外
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## 結論

在本文中，我們介紹了在 Aspose.Tasks for .NET 中處理行事曆異常的各個面向。透過遵循提供的步驟，您可以有效地管理專案進度中的異常情況，確保準確表示工作時間和特殊事件。

## 常見問題解答

### Q1：我可以在一個行事曆中新增多個例外嗎？

A1：是的，您可以在日曆上新增多個例外，以適應各種特殊日期或時段。

### Q2：如何檢查特定日期是否異常？

 A2：您可以使用`CheckException()`方法來驗證特定日期是否屬於例外情況。

### 問題 3：是否可以從日曆中刪除現有的例外？

 A3：是的，您可以透過訪問`Exceptions`收集日曆並使用`Remove()`方法。

### 問題 4：支援哪些類型的日曆例外？

A4：Aspose.Tasks支援各種類型的異常，包括每日、每週、每月和每年的異常，為定義異常規則提供了靈活性。

### Q5：我可以自訂特定例外日期的工作時間嗎？

A5：是的，您可以使用 Aspose.Tasks 提供的適當方法為各個例外日期定義自訂工作時間。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

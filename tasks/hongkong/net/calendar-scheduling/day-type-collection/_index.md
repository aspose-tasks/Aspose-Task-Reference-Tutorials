---
title: 在 Aspose.Tasks 中管理日期類型集合
linktitle: 在 Aspose.Tasks 中管理日期類型集合
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中有效管理日期類型集合。輕鬆建立、修改和操作日曆例外。
weight: 28
url: /zh-hant/net/calendar-scheduling/day-type-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理日期類型集合

## 介紹

 Aspose.Tasks for .NET 提供了管理日期類型集合的強大功能，這對於在專案管理應用程式中定義每週日曆例外至關重要。在本教程中，我們將探討如何利用`DayTypeCollection`高效上課。 

## 先決條件

在繼續學習本教程之前，請確保您符合以下先決條件：

1. Visual Studio：確保您的系統上安裝了 Visual Studio。
2.  Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks for .NET 函式庫[這裡](https://releases.aspose.com/tasks/net/).
3. C# 基礎：熟悉 C# 程式語言和 .NET 框架概念。

## 導入命名空間

首先，您需要將必要的命名空間匯入到您的 C# 專案中：

```csharp
using Aspose.Tasks;
using System;


```

現在，讓我們將提供的範例分解為多個步驟：

## 第 1 步：載入項目並存取日曆

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

此步驟初始化一個新的專案實例並透過其 UID 檢索日曆。

## 第 2 步：遍歷日曆異常

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

在這裡，我們遍歷每個日曆異常並列印其名稱和關聯的日期類型。

## 步驟 3：修改日曆例外

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

此步驟示範如何透過新增、刪除或更新日期類型來修改日曆例外。

## 第 4 步：建立和操作新的日曆例外

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

在最後一步中，我們建立新的日曆例外並透過新增和複製日期類型來操作它們。

## 結論

總之，在 Aspose.Tasks for .NET 中管理日期類型集合對於在專案管理應用程式中定義和修改每週行事曆例外至關重要。透過遵循本教程中提供的逐步指南，您可以有效地利用`DayTypeCollection`類別來處理各種日曆操作。

## 常見問題解答

### Q1：Aspose.Tasks for .NET 可用於以程式設計方式建立甘特圖嗎？

A1：是的，Aspose.Tasks for .NET 提供了 API 來在 .NET 應用程式中建立和操作甘特圖。

### Q2：Aspose.Tasks for .NET 是否與 .NET Core 和 .NET Framework 相容？

A2：是的，Aspose.Tasks for .NET 同時支援 .NET Core 和 .NET Framework。

### Q3：如何獲得 Aspose.Tasks for .NET 支援？

 A3：您可以透過訪問獲得支持[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)您可以在其中提出問題並與其他用戶互動。

### Q4：Aspose.Tasks for .NET 提供免費試用嗎？

 A4：是的，您可以從以下位置獲得 Aspose.Tasks for .NET 的免費試用版：[這裡](https://releases.aspose.com/).

### Q5：我可以購買 Aspose.Tasks for .NET 的臨時授權嗎？

 A5：是的，臨時許可證可以從[阿斯普斯網站](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

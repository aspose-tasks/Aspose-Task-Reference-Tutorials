---
date: 2026-04-09
description: 學習如何在 .NET 專案中使用 Aspose.Tasks 設定標準行事曆及管理專案假期，以實現精確排程。
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: 在 Aspose.Tasks 中設定標準行事曆並處理例外
second_title: Aspose.Tasks .NET API
title: 設定標準行事曆並在 Aspose.Tasks 中處理例外
url: /zh-hant/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定標準行事曆並處理 Aspose.Tasks 中的例外

## 介紹

精確的排程是任何成功專案的基礎，而實際的計畫常因假期、特殊活動或突發停工而需要偏離預設工作行事曆。Aspose.Tasks for .NET 可輕鬆 **設定標準行事曆**，並在其上層疊自訂例外。於本教學中，您將學習如何載入專案行事曆、設定標準行事曆，以及透過 Calendar Exception Collection 功能管理專案假期。

## 快速解答
- **「設定標準行事曆」的作用是什麼？** 它會在您加入自訂例外之前，將行事曆重設為預設工作時間（上午 9 時至下午 5 時，星期一至星期五）。  
- **哪個方法可清除現有例外？** `Calendar.Exceptions.Clear()` 會移除所有先前定義的例外。  
- **如何新增假期？** 建立 `CalendarException`，將 `DayWorking = false`，然後將其加入集合。  
- **變更後需要重新載入專案嗎？** 不需要，變更會直接套用到記憶體中的 `Project` 物件。  
- **需要哪些函式庫？** Aspose.Tasks for .NET（任何支援的 .NET 版本）以及 `System` 命名空間。

## 前置條件

在深入程式碼之前，請確保您已具備：

1. **Aspose.Tasks for .NET** – 前往[此處](https://releases.aspose.com/tasks/net/)下載。  
2. 具備 **C#** 基礎知識 – 您將撰寫幾段簡短程式碼。  
3. 開發環境，例如 **Visual Studio** 或 **JetBrains Rider**。

## 匯入命名空間

這些 `using` 指示可讓您存取操作行事曆所需的類別。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 什麼是行事曆例外？

*行事曆例外* 代表正常工作排程被變更的期間，例如全公司放假或臨時加班排程。透過將例外加入行事曆，您可以在不改變基礎行事曆的情況下模擬現實世界的限制。

## 如何在 Aspose.Tasks 中設定標準行事曆

第一步是載入您的專案檔案，並取得要操作的行事曆。

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### 步驟 1：清除現有例外並重設為標準行事曆

在加入新規則之前，先清除任何舊的例外並 **設定標準行事曆** 設定是個好習慣，這可確保基線乾淨。

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### 步驟 2：定義工作時間例外

有時您需要建立臨時排程（例如產品上市的延長工時）。以下程式碼片段定義了一個跨數天且包含每日兩段工作時間的工作時間例外。

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

### 步驟 3：新增非工作時間例外（假期）

要 **管理專案假期**，請建立 `DayWorking` 為 `false` 的例外。下例新增了一個為期兩天的假期區塊。

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### 步驟 4：顯示行事曆例外（驗證）

加入例外後，您通常會想驗證它們是否正確記錄。以下迴圈會將每個例外的詳細資訊印出至主控台。

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

### 步驟 5：移除所有例外（清理）

如果需要將行事曆恢復至原始狀態，可程式化地移除所有例外。

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| 儲存後例外未顯示 | 修改後未儲存專案 | 在完成變更後呼叫 `project.Save("output.mpp")`。 |
| 重疊的例外導致非預期的工作時數 | Aspose.Tasks 會以最後加入的例外為準處理重疊期間 | 請謹慎安排 `Add` 呼叫的順序，或手動調整優先順序。 |
| `MakeStandardCalendar` 會重設自訂工作時間 | 此方法會刻意清除自訂時間；如有需要，請在呼叫後重新加入。 | 在呼叫 `MakeStandardCalendar` 後再加入自訂的 `WorkingTime` 物件。 |

## 常見問答

**Q: 我可以在同一個行事曆中加入多個例外嗎？**  
A: 可以，您可以使用 `AddRange` 方法將多個例外加入行事曆。

**Q: 如何處理週期性例外，例如每週假期？**  
A: 您可以以程式方式計算週期性例外，並使用自訂邏輯將它們加入行事曆。

**Q: 是否可以從外部來源匯入行事曆例外？**  
A: 可以，您可以從資料庫、CSV 檔等外部來源讀取行事曆例外，並整合至您的專案。

**Q: 行事曆中若出現重疊的例外會發生什麼情況？**  
A: Aspose.Tasks for .NET 允許您透過設定優先順序或依專案需求解決衝突來處理重疊例外。

**Q: 我可以為例外內的每一天自訂工作時間嗎？**  
A: 可以，您可以在例外內為個別日期指定自訂工作時間，以符合特定排程需求。

## 結論

先 **設定標準行事曆**，再層疊自訂例外，您即可完整掌控專案排程，輕鬆 **管理專案假期** 以及其他特殊時程。Aspose.Tasks 的 Calendar Exception Collection 提供了一種乾淨且程式化的方式，直接在 .NET 應用程式中建模現實世界的行事曆。

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
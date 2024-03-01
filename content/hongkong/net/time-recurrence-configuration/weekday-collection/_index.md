---
title: 掌握 Aspose.Tasks 中的工作日
linktitle: Aspose.Tasks 中工作日的集合
second_title: Aspose.Tasks .NET API
description: 發現 Aspose.Tasks for .NET 在輕鬆管理工作日方面的強大功能。自訂工作日、刪除週末並輕鬆建立專門的日曆。
type: docs
weight: 11
url: /zh-hant/net/time-recurrence-configuration/weekday-collection/
---
## 介紹
Aspose.Tasks for .NET 是一個功能強大的函式庫，可促進專案管理資料的高效操作。在本教程中，我們將探索 Aspose.Tasks 中的工作日集合，使您能夠自訂工作日、刪除週末以及建立專門的日曆來滿足您的專案要求。無論您是經驗豐富的開發人員還是新手，本逐步指南都將引導您完成在 Aspose.Tasks for .NET 中處理工作日的過程。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- 安裝 Aspose.Tasks for .NET 函式庫。您可以從[Aspose.Tasks for .NET 下載頁面](https://releases.aspose.com/tasks/net/).
- 熟悉C#程式語言。
- 整合開發環境 (IDE)，例如 Visual Studio。
## 導入命名空間
首先將必要的命名空間匯入到您的 C# 專案中：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 步驟1：建立專案實例
初始化一個新的 Aspose.Tasks 專案：
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## 第 2 步：訪問日曆
檢索專案日曆：
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## 第 3 步：自訂工作日
清除現有工作日並設定預設工作日：
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
//以同樣的方式添加其他工作日...
```
## 第 4 步：新增工作時間
新增特定工作日的工作時間：
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## 第5步：顯示日曆資訊
將日曆詳細資訊輸出到控制台：
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
//顯示每個工作日和工作時間...
```
## 第 6 步：刪除週末
從工作日中刪除週六和週日：
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## 第 7 步：顯示更新的工作時間
輸出刪除週末後更新的工作時間：
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
//顯示每個更新的工作日和工作時間...
```
## 第 8 步：建立 24 小時行事曆
建立 24 小時日曆並複製工作日：
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## 結論
在本教程中，我們探索了 Aspose.Tasks for .NET 在專案行事曆中管理工作日的強大功能。從客製化工作日到創建專門的 24 小時日曆，Aspose.Tasks 簡化了流程，為專案管理提供了靈活性和控制力。
## 經常問的問題
### Q：我可以將 Aspose.Tasks for .NET 與其他程式語言一起使用嗎？
答：Aspose.Tasks 主要支援 .NET 語言，但也提供 Java 版本。
### Q：Aspose.Tasks for .NET 有沒有免費試用版？
答：是的，您可以從以下網站下載免費試用版：[Aspose.Tasks 發佈頁面](https://releases.aspose.com/).
### Q：如何獲得 Aspose.Tasks for .NET 支援？
答：訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求社區支持或考慮購買支持計劃。
### Q：在哪裡可以找到 Aspose.Tasks for .NET 的綜合文件？
答：請參閱[.NET 文件的 Aspose.Tasks](https://reference.aspose.com/tasks/net/)獲取詳細資訊。
### Q：如何取得 Aspose.Tasks for .NET 的臨時授權？
答：您可以從以下機構獲得臨時許可證：[臨時許可證頁面](https://purchase.aspose.com/temporary-license/).
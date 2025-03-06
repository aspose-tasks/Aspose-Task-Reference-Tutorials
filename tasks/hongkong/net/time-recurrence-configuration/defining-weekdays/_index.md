---
title: 在 Aspose.Tasks for .NET 中掌握工作日
linktitle: 在 Aspose.Tasks 中定義工作日
second_title: Aspose.Tasks .NET API
description: 探索在 Aspose.Tasks .NET 中定義工作日的強大功能。請按照我們的詳細教學來有效管理專案日曆、自訂工作時間等。
type: docs
weight: 10
url: /zh-hant/net/time-recurrence-configuration/defining-weekdays/
---
## 介紹
如果您正在使用 Aspose.Tasks for .NET 進入專案管理世界，那麼理解和操作工作日是一個至關重要的方面。在專案日曆中有效管理和自訂工作日可以顯著影響專案時間表。在本教程中，我們將指導您完成使用 Aspose.Tasks 定義工作日的流程，並提供逐步說明和範例，以便更加清晰。
## 先決條件
在我們開始這趟旅程之前，請確保您符合以下先決條件：
- 對 C# 程式語言有基本了解。
- 安裝了 .NET 函式庫的 Aspose.Tasks。如果沒有，請從以下位置下載[這裡](https://releases.aspose.com/tasks/net/).
## 導入命名空間
首先將必要的命名空間匯入到您的專案中：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 檢查平日平等
```csharp
//您的文件目錄
String DataDir = "Your Document Directory";
//載入專案文件
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
//工作日訪問
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
//根據各種屬性檢查相等性
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
//為DayWorking、FromDate、ToDate 和WorkingTimes 新增類似的輸出語句
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. 克隆工作日
```csharp
//載入專案文件
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
//創建工作日的深層副本
var weekDay2 = weekDay1.Clone();
//兩個工作日的輸出屬性
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
//為DayWorking、FromDate、ToDate 和WorkingTimes 新增類似的輸出語句
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. 取得工作日的哈希碼
```csharp
//載入專案文件
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
//兩個工作日的輸出屬性
//為DayWorking、FromDate、ToDate 和WorkingTimes 新增類似的輸出語句
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. 建立一個包含已定義工作日的新日曆
```csharp
//建立一個新項目
var project = new Project();
//定義日曆
var calendar = project.Calendars.Add("Calendar1");
//新增工作日和例外日
//為 FromDate 和 ToDate 新增類似的輸出語句
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
//設定週五的工作時間
//為DayWorking、FromDate、ToDate 和WorkingTimes 新增類似的輸出語句
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5.設定一天的預設工作時間
```csharp
//建立一個新項目
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
//新增週一至週五的預設工作時間
//為DayWorking、FromDate、ToDate 和WorkingTimes 新增類似的輸出語句
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
//週二、週三、週四和週五重複
//設定週六、週日為非工作日
//為DayWorking、FromDate、ToDate 和WorkingTimes 新增類似的輸出語句
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## 結論
在本教程中，我們介紹了在 Aspose.Tasks for .NET 中定義工作日的基本面向。掌控工作日是有效專案管理的關鍵技能。嘗試提供的範例，根據您的專案需求進行定制，並釋放 Aspose.Tasks 的全部潛力。
## 常見問題解答
### 我可以定義每天的自訂工作時間嗎？
是的，您可以使用提供的範例為特定工作日設定自訂工作時間。
### 是否可以在日曆中新增多個例外日子？
絕對地。修改第四個範例中的程式碼以包含其他例外日期。
### 如何從日曆中刪除特定工作日？
利用 Aspose.Tasks 函式庫提供的適當方法根據需要刪除工作日。
### 對工作日所做的更改是否會保留在專案文件中？
是的，對工作日的任何修改都會在儲存時反映在專案文件中。
### 我可以將 Aspose.Tasks 與其他程式語言一起使用嗎？
Aspose.Tasks 支援各種程式語言，但此處的範例專門針對 .NET。
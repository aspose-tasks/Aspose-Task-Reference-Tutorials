---
title: 掌握 Aspose.Tasks 的工作時間
linktitle: Aspose.Tasks 中工作時間的集合
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 在有效管理專案時程方面的強大功能。自訂日曆、設定工作時間並輕鬆簡化您的專案。
type: docs
weight: 14
url: /zh-hant/net/time-recurrence-configuration/working-time-collection/
---
## 介紹
您是否希望掌握在 Aspose.Tasks for .NET 中管理工作時間的藝術？別再猶豫了！在本逐步指南中，我們將深入研究使用 Aspose.Tasks 收集工作時間的複雜性，使您能夠有效地處理自訂日曆並簡化專案時間表。
## 先決條件
在我們開始這趟旅程之前，請確保您具備以下先決條件：
-  Aspose.Tasks for .NET 函式庫：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[Aspose.Tasks 發佈頁面](https://releases.aspose.com/tasks/net/).
- 工作環境：設定適當的開發環境，最好使用.NET相容的IDE。
## 導入命名空間
在您的專案中，匯入必要的命名空間以存取 Aspose.Tasks 功能：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
現在，讓我們將教程分解為多個步驟，以確保順利的學習體驗。
## 第 1 步：建立自訂日曆
首先建立一個新專案並在其中新增自訂日曆：
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## 第 2 步：定義工作日
設定預設工作日為週一至週五：
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## 步驟 3：配置週六工作時間
指定週六的工作時間：
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## 第 4 步：列印週六工作時間
列印週六配置的工作時間：
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## 步驟 5：設定週日工作時間
定義週日的工作時間：
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## 第 6 步：列印週日工作時間
列印週日配置的工作時間：
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## 第 7 步：將自訂日期新增至日曆中
在日曆中包含配置的星期六和星期日：
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## 第 8 步：遍歷工作時間
遍歷工作時間並在日曆中顯示每天的工作時間：
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
既然您已成功完成這些步驟，您就可以利用 Aspose.Tasks for .NET 的強大功能來有效管理工作時間。
## 結論
掌握 Aspose.Tasks 中的工作時間集合可讓您自訂專案行事曆，確保精確的排程和高效的資源利用。借助從本綜合指南中獲得的知識，充滿信心地投入您的專案。
## 經常問的問題
### Aspose.Tasks適合大型專案管理嗎？
是的，Aspose.Tasks 旨在處理不同規模的項目，為高效的專案管理提供強大的功能。
### 我可以將 Aspose.Tasks 與其他 .NET 函式庫整合嗎？
當然！ Aspose.Tasks 與其他 .NET 函式庫無縫集成，增強了其多功能性和相容性。
### Aspose.Tasks 多久更新一次？
 Aspose.Tasks 定期更新以納入新功能、增強功能和相容性改進。檢查[發布頁面](https://releases.aspose.com/tasks/net/)了解最新動態。
### Aspose.Tasks 是否有免費試用版？
是的，您可以透過造訪免費試用來探索 Aspose.Tasks[這個連結](https://releases.aspose.com/).
### 我可以在哪裡尋求 Aspose.Tasks 的支援？
如有任何疑問或幫助，請訪問[Aspose.Tasks 支援論壇](https://forum.aspose.com/c/tasks/15).
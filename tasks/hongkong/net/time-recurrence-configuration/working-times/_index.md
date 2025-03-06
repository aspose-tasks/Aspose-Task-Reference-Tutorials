---
title: 在 Aspose.Tasks 中配置工作時間
linktitle: 在 Aspose.Tasks 中配置工作時間
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks 增強 .NET 中的專案排程。輕鬆配置工作時間以實現精確的資源管理。立即下載庫！
weight: 13
url: /zh-hant/net/time-recurrence-configuration/working-times/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中配置工作時間

## 介紹
在專案管理中，精確控制工作時間對於準確調度和資源分配至關重要。 Aspose.Tasks for .NET 提供了一個強大的解決方案來處理專案中的工作時間資訊。本教學將引導您完成在 .NET 環境中使用 Aspose.Tasks 配置工作時間的過程。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
- 對 C# 程式語言有基本了解。
- 安裝了 .NET 函式庫的 Aspose.Tasks。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
- 設定 Visual Studio 或任何首選的 C# 開發環境。
## 導入命名空間
首先匯入必要的命名空間來存取 Aspose.Tasks 功能：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## 第 1 步：建立日曆
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
在這裡，我們啟動一個新項目，並基於標準日曆建立一個名為「MyCalendar」的日曆。此日曆將用於定義具體的工作時間。

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## 第 2 步：顯示工作週資訊
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
此步驟列印指定日曆中的總工作天數。
## 第 3 步：工作時間詳情
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
在這一部分中，我們迭代一周中的每一天，列印日期類型和相關的工作時間。您可以根據您的專案要求自訂每個工作日的工作時間。
## 結論
在 Aspose.Tasks for .NET 中有效配置工作時間可確保準確的專案規劃和資源管理。透過遵循此逐步指南，您可以將工作時間調整無縫整合到專案工作流程中。
## 經常問的問題
### Aspose.Tasks適合大型專案管理嗎？
是的，Aspose.Tasks 旨在處理各種規模的項目，為高效的專案管理提供強大的功能。
### 我可以為不同的團隊成員設定不同的工作時間嗎？
絕對地。您可以根據每個資源自訂工作時間，從而實現個人化的時間表。
### Aspose.Tasks 是否支援與其他專案管理工具整合？
是的，Aspose.Tasks 有助於與各種專案管理工具集成，增強互通性。
### 是否可以匯入/匯出不同格式的專案資料？
Aspose.Tasks支援多種檔案格式，實現專案資料的無縫匯入/匯出操作。
### Aspose.Tasks 更新發佈的頻率是多少？
定期發布更新以確保與最新技術的兼容性並解決用戶回饋。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

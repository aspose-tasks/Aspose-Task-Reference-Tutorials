---
date: 2026-04-13
description: 學習如何在 Aspose.Tasks for .NET 中設定工作時間與管理日曆集合。匯入 Microsoft Project 的日曆、移除日曆專案，並可輕鬆依名稱取得日曆。
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: 在 Aspose.Tasks 中管理日曆集合
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 日曆集合中設定工作時間
url: /zh-hant/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定 Aspose.Tasks 行事曆集合的工作時間

在本教學中，您將學習如何 **設定工作時間** 以及使用 Aspose.Tasks for .NET 管理行事曆集合。行事曆定義工作日、假期與例外情況，精通它們即可精確控制專案排程。我們亦會示範如何從 Microsoft Project 匯入行事曆、從專案中移除行事曆，以及依名稱取得行事曆。

## 快速解答
- **什麼是行事曆的主要類別？** `Project.Calendars` collection.
- **如何設定工作時間？** 建立或修改 `Calendar` 物件並定義其 `WorkingTime`。
- **可以從 Microsoft Project 匯入行事曆嗎？** 可以 – 載入 MPP 檔案並存取其行事曆。
- **如何從專案中移除行事曆？** 使用 `Project.Calendars.Remove(calendar)`。
- **如何依名稱取得行事曆？** 呼叫 `Project.Calendars.GetByName("YourCalendar")`。

## 前置條件

在開始之前，請確保您具備以下條件：

1. Visual Studio：安裝 Visual Studio 或任何其他相容的 .NET 開發 IDE。  
2. Aspose.Tasks for .NET：從 [此處](https://releases.aspose.com/tasks/net/) 下載並安裝 Aspose.Tasks for .NET。  
3. 基本的 C# 知識：熟悉 C# 程式語言將會有幫助。

## 匯入命名空間

首先，讓我們匯入使用 Aspose.Tasks 所需的命名空間：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## 建立新行事曆

### 步驟 1：初始化新的 `Project` 物件。
```csharp
var project = new Project();
```

### 步驟 2：將行事曆加入專案的行事曆集合。
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### 步驟 3：遍歷行事曆並顯示其名稱。
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 如何為行事曆設定工作時間？

要 **設定工作時間**，您需要修改 `Calendar` 的 `WorkingTime` 集合。  
例如，您可以定義標準的上午 9 點至下午 5 點工作日，或加入自訂例外。  
此段程式碼與稍後建立標準行事曆的範例相同。

## 用新行事曆取代現有行事曆

### 步驟 1：載入現有專案。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步驟 2：移除現有的行事曆（若存在）。  
此示範 **移除行事曆專案** 的情境。
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### 步驟 3：加入新行事曆。
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## 依名稱或 ID 取得行事曆

### 步驟 1：載入專案。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步驟 2：依名稱或 UID 取得行事曆。  
此說明 **依名稱取得行事曆** 的操作。
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### 步驟 3：顯示行事曆詳細資訊。
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## 遍歷行事曆

### 步驟 1：載入專案。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步驟 2：取得行事曆的數量。
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### 步驟 3：遍歷行事曆集合並顯示名稱。
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 建立標準行事曆

### 步驟 1：初始化新專案。
```csharp
var project = new Project();
```

### 步驟 2：定義新行事曆並將其設為標準。
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### 步驟 3：儲存專案。
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## 常見問題與解決方案

- **使用 `GetByName` 時找不到行事曆** – 確認名稱完全相同且大小寫與加入時一致。  
- **工作時間未套用** – 設定 `WorkingTime` 後，請記得儲存專案；否則變更僅保留在記憶體中。  
- **從 MPP 檔匯入行事曆失敗** – 請確認來源檔案為有效的 Microsoft Project 檔，且您具有讀取權限。

## 常見問答

### Q1：我可以在 Aspose.Tasks 中建立自訂工作日嗎？

A1：可以，您可以透過在行事曆加入例外來建立自訂工作日。

### Q2：是否可以從 Microsoft Project 檔案匯入行事曆？

A2：當然可以，Aspose.Tasks 支援從 Microsoft Project 檔案匯入行事曆。

### Q3：我該如何從專案中移除特定行事曆？

A3：您可以先從集合中取得該行事曆，然後呼叫 `Remove` 方法將其移除。

### Q4：Aspose.Tasks 是否支援將行事曆匯出為不同格式？

A4：是的，Aspose.Tasks 可將行事曆匯出為 XML、MPP 等多種格式。

### Q5：我可以為行事曆中的特定日期自訂工作時間嗎？

A5：當然可以，您可透過在行事曆中加入例外，為個別日期定義工作時間。

## 常見問題

**Q：設定 24 小時輪班行事曆的最佳方式是什麼？**  
A：建立新行事曆，清除現有的 `WorkingTime` 項目，然後為每個工作日新增一個從 00:00 到 24:00 的 `WorkingTime` 範圍。

**Q：我可以將行事曆從一個專案複製到另一個嗎？**  
A：可以—使用 `project.Save` 將行事曆匯出為 XML，然後使用 `new Project(xmlPath)` 匯入至另一個專案。

**Q：如何以程式方式匯入 Microsoft Project 的行事曆？**  
A：使用 `new Project("source.mpp")` 載入 MPP 檔案；行事曆即可透過 `project.Calendars` 取得。

**Q：專案中的行事曆數量有限制嗎？**  
A：實際上沒有；只要記憶體允許，集合可容納任意數量的行事曆，但為了效能建議保持列表可管理。

**Q：對行事曆的變更會自動更新使用該行事曆的工作項目嗎？**  
A：會的—在儲存專案後，連結至該行事曆的工作項目會反映更新後的工作時間。

---

**最後更新：** 2026-04-13  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
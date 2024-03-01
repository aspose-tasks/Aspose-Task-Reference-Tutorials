---
title: 在 Aspose.Tasks 中管理行事曆集合
linktitle: 在 Aspose.Tasks 中管理行事曆集合
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中有效地管理行事曆集合。輕鬆建立、修改和操作日曆。
type: docs
weight: 11
url: /zh-hant/net/calendar-scheduling/calendar-collection/
---
## 介紹

在本教程中，我們將探討如何在 Aspose.Tasks for .NET 中管理行事曆集合。日曆在專案管理、定義工作日、假期和例外情況中發揮著至關重要的作用。 Aspose.Tasks 提供了強大的功能來操作專案中的日曆。

## 先決條件

在我們開始之前，請確保您具備以下條件：

1. Visual Studio：安裝 Visual Studio 或任何其他相容的 IDE 以進行 .NET 開發。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[這裡](https://releases.aspose.com/tasks/net/).
3. 對 C# 的基本了解：熟悉 C# 程式語言將會很有幫助。

## 導入命名空間

首先，讓我們匯入必要的命名空間來使用 Aspose.Tasks：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## 建立新日曆

### 步驟一：初始化一個新的`Project` object.
```csharp
var project = new Project();
```

### 步驟 2：將日曆新增至項目的日曆集合。
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### 第 3 步：遍歷日曆並顯示它們的名稱。
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 用新日曆取代日曆

### 第 1 步：載入現有項目。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步驟 2：刪除現有日曆（如果存在）。
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### 步驟 3：新增日曆。
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## 透過名稱或 ID 取得日曆

### 第 1 步：載入項目。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步驟 2：按名稱或 UID 擷取日曆。
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### 步驟 3：顯示日曆詳細資料。
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## 迭代日曆

### 第 1 步：載入項目。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步驟 2：檢索日曆的計數。
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### 步驟 3：迭代日曆集合和顯示名稱。
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 製作標準日曆

### 步驟1：初始化一個新項目。
```csharp
var project = new Project();
```

### 第 2 步：定義新日曆並使其成為標準。
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### 步驟 3：儲存項目。
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## 結論

在 Aspose.Tasks for .NET 中管理行事曆集合對於有效的專案管理至關重要。透過提供的功能，您可以根據專案要求有效地建立、修改和操作日曆。

## 常見問題解答

### Q1：我可以在 Aspose.Tasks 中建立自訂工作日嗎？

A1：是的，您可以透過向日曆新增例外來建立自訂工作日。

### 問題 2：是否可以從 Microsoft Project 檔案匯入行事曆？

A2：當然，Aspose.Tasks 支援從 Microsoft Project 檔案匯入日曆。

### 問題 3：如何從專案中刪除特定日曆？

 A3：您可以透過從集合中取得日曆然後調用`Remove`方法。

### Q4：Aspose.Tasks 支援將日曆匯出為不同格式嗎？

A4：是的，Aspose.Tasks 允許將日曆匯出為各種格式，如 XML、MPP 等。

### Q5：我可以在日曆中自訂特定日期的工作時間嗎？

A5：當然，您可以使用日曆中的例外情況來定義單日的工作時間。
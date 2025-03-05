---
title: 在 Aspose.Tasks 中管理日历集合
linktitle: 在 Aspose.Tasks 中管理日历集合
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中高效管理日历集合。轻松创建、修改和操作日历。
type: docs
weight: 11
url: /zh/net/calendar-scheduling/calendar-collection/
---
## 介绍

在本教程中，我们将探讨如何在 Aspose.Tasks for .NET 中管理日历集合。日历在项目管理、定义工作日、假期和例外情况中发挥着至关重要的作用。 Aspose.Tasks 提供了强大的功能来操作项目中的日历。

## 先决条件

在我们开始之前，请确保您具备以下条件：

1. Visual Studio：安装 Visual Studio 或任何其他兼容的 IDE 以进行 .NET 开发。
2.  Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET[这里](https://releases.aspose.com/tasks/net/).
3. 对 C# 的基本了解：熟悉 C# 编程语言将会很有帮助。

## 导入命名空间

首先，让我们导入必要的命名空间来使用 Aspose.Tasks：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## 创建新日历

### 步骤一：初始化一个新的`Project` object.
```csharp
var project = new Project();
```

### 步骤 2：将日历添加到项目的日历集合中。
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### 第 3 步：遍历日历并显示它们的名称。
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 用新日历替换日历

### 第 1 步：加载现有项目。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步骤 2：删除现有日历（如果存在）。
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### 步骤 3：添加新日历。
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## 通过名称或 ID 获取日历

### 第 1 步：加载项目。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步骤 2：按名称或 UID 检索日历。
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### 步骤 3：显示日历详细信息。
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## 迭代日历

### 第 1 步：加载项目。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步骤 2：检索日历的计数。
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### 步骤 3：迭代日历集合和显示名称。
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 制作标准日历

### 步骤1：初始化一个新项目。
```csharp
var project = new Project();
```

### 第 2 步：定义新日历并使其成为标准。
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### 步骤 3：保存项目。
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## 结论

在 Aspose.Tasks for .NET 中管理日历集合对于有效的项目管理至关重要。通过提供的功能，您可以根据项目要求高效地创建、修改和操作日历。

## 常见问题解答

### Q1：我可以在 Aspose.Tasks 中创建自定义工作日吗？

A1：是的，您可以通过向日历添加例外来创建自定义工作日。

### 问题 2：是否可以从 Microsoft Project 文件导入日历？

A2：当然，Aspose.Tasks 支持从 Microsoft Project 文件导入日历。

### 问题 3：如何从项目中删除特定日历？

 A3：您可以通过从集合中获取日历然后调用`Remove`方法。

### Q4：Aspose.Tasks 支持将日历导出为不同格式吗？

A4：是的，Aspose.Tasks 允许将日历导出为各种格式，如 XML、MPP 等。

### Q5：我可以在日历中自定义特定日期的工作时间吗？

A5：当然，您可以使用日历中的例外情况来定义单日的工作时间。
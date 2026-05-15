---
date: 2026-04-13
description: 了解如何在 Aspose.Tasks for .NET 中设置工作时间并管理日历集合。轻松导入 Microsoft Project 日历、删除项目日历以及按名称获取日历。
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: 在 Aspose.Tasks 中管理日历集合
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 日历集合中设置工作时间
url: /zh/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 日历集合中设置工作时间

在本教程中，您将学习如何 **设置工作时间** 并使用 Aspose.Tasks for .NET 管理日历集合。日历定义工作日、假期和例外情况，掌握它们即可精确控制项目进度。我们还将演示如何从 Microsoft Project 导入日历、从项目中删除日历以及按名称获取日历。

## 快速答案
- **日历的主要类是什么？** `Project.Calendars` 集合。
- **如何设置工作时间？** 创建或修改 `Calendar` 对象并定义其 `WorkingTime`。
- **我可以从 Microsoft Project 导入日历吗？** 可以——加载 MPP 文件并访问其日历。
- **如何从项目中删除日历？** 使用 `Project.Calendars.Remove(calendar)`。
- **如何按名称检索日历？** 调用 `Project.Calendars.GetByName("YourCalendar")`。

## 前提条件

在开始之前，请确保您具备以下条件：

1. Visual Studio：安装 Visual Studio 或任何其他兼容 .NET 开发的 IDE。  
2. Aspose.Tasks for .NET：从 [此处](https://releases.aspose.com/tasks/net/) 下载并安装 Aspose.Tasks for .NET。  
3. 基本的 C# 知识：熟悉 C# 编程语言将有所帮助。

## 导入命名空间

首先，让我们导入使用 Aspose.Tasks 所需的命名空间：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## 创建新日历

### 步骤 1：初始化一个新的 `Project` 对象。
```csharp
var project = new Project();
```

### 步骤 2：向项目的日历集合添加日历。
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### 步骤 3：遍历日历并显示其名称。
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 如何为日历设置工作时间？

要 **设置工作时间**，您需要修改 `Calendar` 的 `WorkingTime` 集合。  
例如，您可以定义标准的上午 9 点至下午 5 点工作日，或添加自定义例外。  
此代码与我们后面创建标准日历时展示的示例完全相同。

## 用新日历替换现有日历

### 步骤 1：加载现有项目。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步骤 2：删除现有日历（如果存在）。  
此示例演示了 **删除项目日历** 场景。
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

## 按名称或 ID 获取日历

### 步骤 1：加载项目。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步骤 2：按名称或 UID 检索日历。  
此示例说明了 **按名称获取日历** 操作。
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

## 遍历日历

### 步骤 1：加载项目。
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### 步骤 2：获取日历数量。
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### 步骤 3：遍历日历集合并显示名称。
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## 创建标准日历

### 步骤 1：初始化新项目。
```csharp
var project = new Project();
```

### 步骤 2：定义新日历并将其设为标准。
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### 步骤 3：保存项目。
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## 常见问题及解决方案

- **使用 `GetByName` 时未找到日历** —— 确保名称完全匹配添加日历时使用的大小写。  
- **工作时间未生效** —— 设置 `WorkingTime` 后，请记得保存项目；否则更改仅保留在内存中。  
- **从 MPP 文件导入日历失败** —— 请确认源文件是有效的 Microsoft Project 文件，并且您具有读取权限。

## 常见问答

### Q1：我可以在 Aspose.Tasks 中创建自定义工作日吗？

A1：可以，您可以通过向日历添加例外来创建自定义工作日。

### Q2：是否可以从 Microsoft Project 文件导入日历？

A2：当然，Aspose.Tasks 支持从 Microsoft Project 文件导入日历。

### Q3：如何从项目中删除特定的日历？

A3：您可以先从集合中获取该日历，然后调用 `Remove` 方法将其删除。

### Q4：Aspose.Tasks 是否支持将日历导出为不同格式？

A4：是的，Aspose.Tasks 允许将日历导出为 XML、MPP 等多种格式。

### Q5：我可以为日历中的特定日期自定义工作时间吗？

A5：当然，您可以通过在日历中添加例外来为单独的日期定义工作时间。

## 常见问题

**Q：设置 24 小时轮班日历的最佳方法是什么？**  
A：创建一个新日历，清除现有的 `WorkingTime` 条目，然后为每个工作日添加一个从 00:00 到 24:00 的单一 `WorkingTime` 区间。

**Q：我可以将日历从一个项目复制到另一个项目吗？**  
A：可以——使用 `project.Save` 将日历导出为 XML，然后使用 `new Project(xmlPath)` 将其导入到另一个项目中。

**Q：如何以编程方式导入 Microsoft Project 的日历？**  
A：使用 `new Project("source.mpp")` 加载 MPP 文件；日历可通过 `project.Calendars` 获得。

**Q：项目中日历的数量有上限吗？**  
A：实际上没有；该集合可以容纳尽可能多的日历，只受内存限制，但为保证性能应保持列表可管理。

**Q：对日历的更改会自动更新使用该日历的任务吗？**  
A：是的——在保存项目后，关联到该日历的任务会反映更新后的工作时间。

---

**最后更新：** 2026-04-13  
**测试环境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
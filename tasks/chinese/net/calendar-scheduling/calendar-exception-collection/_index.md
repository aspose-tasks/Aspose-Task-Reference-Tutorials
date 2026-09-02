---
date: 2026-04-09
description: 了解如何在 .NET 项目中使用 Aspose.Tasks 设置标准日历并管理项目假期，以实现准确的排程。
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: 在 Aspose.Tasks 中设置标准日历并处理例外
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 中设置标准日历并处理例外情况
url: /zh/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 设置标准日历并处理 Aspose.Tasks 中的例外

## 介绍

准确的进度安排是任何成功项目的基石，实际计划常常需要因假期、特殊活动或意外停工而偏离默认工作日历。Aspose.Tasks for .NET 使得 **设置标准日历** 设置变得简便，并可在其上叠加自定义例外。在本教程中，您将学习如何加载项目日历、设置标准日历，以及通过 Calendar Exception Collection 功能管理项目假期。

## 快速答案
- **设置标准日历 的作用是什么？** 它会在您添加自定义例外之前，将日历重置为默认工作时间（上午 9 点至下午 5 点，周一至周五）。  
- **哪个方法可以清除已有的例外？** `Calendar.Exceptions.Clear()` 会移除所有先前定义的例外。  
- **如何添加假期？** 创建一个 `DayWorking = false` 的 `CalendarException` 并将其添加到集合中。  
- **更改后需要重新加载项目吗？** 不需要，修改会直接应用到内存中的 `Project` 对象。  
- **需要哪些库？** Aspose.Tasks for .NET（任何受支持的 .NET 版本）以及 `System` 命名空间。

## 前置条件

在深入代码之前，请确保您已拥有：

1. **Aspose.Tasks for .NET** – 在此处下载 [here](https://releases.aspose.com/tasks/net/)。  
2. 基本的 **C#** 知识 – 您将编写几段简短的代码片段。  
3. 如 **Visual Studio** 或 **JetBrains Rider** 等开发环境。

## 导入命名空间

这些 `using` 指令为您提供操作日历所需的类。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 什么是日历例外？

*日历例外* 表示正常工作时间被更改的时期，例如全公司假期或临时加班安排。通过向日历添加例外，您可以在不更改基础日历的情况下模拟实际约束。

## 如何在 Aspose.Tasks 中设置标准日历

第一步是加载项目文件并获取您要使用的日历。

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### 步骤 1：清除现有例外并重置为标准日历

在添加新规则之前，最好先清除所有旧的例外并 **设置标准日历** 设置。这可确保一个干净的基准。

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### 步骤 2：定义工作时间例外

有时您需要创建临时日程（例如产品发布的延长工作时间）。下面的代码片段定义了一个跨越数天并包含每日两个工作时段的工作时间例外。

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

### 步骤 3：添加非工作时间例外（假期）

要 **管理项目假期**，请创建 `DayWorking` 为 `false` 的例外。下面的示例添加了一个为期两天的假期块。

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

### 步骤 4：显示日历例外（验证）

添加例外后，您通常会想验证它们是否正确记录。下面的循环将每个例外的详细信息打印到控制台。

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

### 步骤 5：删除所有例外（清理）

如果需要将日历恢复到原始状态，您可以通过编程方式删除所有例外。

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| 保存后例外未出现 | 修改后项目未保存 | 在进行更改后调用 `project.Save("output.mpp")`。 |
| 重叠的例外导致意外的工作时间 | Aspose.Tasks 在重叠期间使用最后添加的例外 | 请仔细安排 `Add` 调用的顺序，或手动调整优先级。 |
| `MakeStandardCalendar` 会重置自定义工作时间 | 它会有意清除自定义时间；如有需要，请在调用后重新添加。 | 在调用 `MakeStandardCalendar` 后添加自定义的 `WorkingTime` 对象。 |

## 常见问答

**问：我可以向单个日历添加多个例外吗？**  
答：是的，您可以使用 `AddRange` 方法向日历添加多个例外。

**问：如何处理重复的例外，例如每周假期？**  
答：您可以通过编程计算重复的例外，并使用自定义逻辑将其添加到日历中。

**问：是否可以从外部来源导入日历例外？**  
答：可以，您可以从数据库或 CSV 文件等外部来源读取日历例外，并将其集成到项目中。

**问：如果日历中存在重叠的例外会怎样？**  
答：Aspose.Tasks for .NET 允许您通过定义优先级或根据项目需求解决冲突来处理重叠的例外。

**问：我可以为例外中的每一天自定义工作时间吗？**  
答：可以，您可以在例外中为各个日期指定自定义工作时间，以满足特定的排程需求。

## 结论

通过先 **设置标准日历**，再叠加自定义例外，您可以完全掌控项目进度安排，从而轻松 **管理项目假期** 以及其他特殊时间线。Aspose.Tasks 中的 Calendar Exception Collection 为在 .NET 应用程序中直接以清晰、可编程的方式建模真实日历提供了便利。

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
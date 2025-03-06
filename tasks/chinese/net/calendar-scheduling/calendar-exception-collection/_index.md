---
title: Aspose.Tasks 中日历异常的集合
linktitle: Aspose.Tasks 中日历异常的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 高效处理 .NET 项目中的日历异常，确保准确的调度和资源管理。
weight: 13
url: /zh/net/calendar-scheduling/calendar-exception-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中日历异常的集合

## 介绍

在项目管理中，精确的调度对于成功至关重要。然而，由于假期、特殊事件或其他因素，现实场景通常需要偏离标准时间表。 Aspose.Tasks for .NET 提供了一个强大的解决方案，通过其日历异常收集功能来管理此类异常。本教程将指导您逐步完成使用此功能的过程。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

1.  Aspose.Tasks for .NET：确保您已安装该库。你可以下载它[这里](https://releases.aspose.com/tasks/net/).
2. C#基础知识：熟悉C#编程语言将有助于理解示例。
3. 开发环境：设置您首选的开发环境，例如 Visual Studio 或 JetBrains Rider。

## 导入命名空间

在开始使用 Aspose.Tasks for .NET 之前，您需要将所需的命名空间导入到您的项目中。此步骤使您能够访问管理日历异常所需的类和方法。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

现在，让我们将提供的示例分解为多个步骤：

## 第 1 步：加载项目并检索日历

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

在此步骤中，我们加载项目文件并通过其 UID 检索所需的日历。

## 第 2 步：清除现有例外情况并设置标准日历

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

此步骤从日历中清除任何现有例外并将其设置为标准配置。

## 步骤 3：定义并添加工作时间例外

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

此步骤定义具有特定开始和结束日期的工作时间例外，以及这些日期内的工作时间，并将其添加到日历中。

## 第 4 步：定义并添加非工作时间例外情况

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

//如果需要，添加更多例外

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

此步骤定义非工作时间例外（例如节假日），并将其添加到日历中。

## 第 5 步：显示日历例外情况

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

此步骤显示添加的日历例外及其详细信息。

## 第 6 步：删除所有异常

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

最后，此步骤从日历中删除所有例外情况。

## 结论

管理日历异常对于准确的项目安排至关重要。 Aspose.Tasks for .NET 通过提供一套全面的功能（包括日历异常集合）来简化此任务。通过遵循本教程中概述的步骤，您可以有效地处理项目中的各种调度方案。

## 常见问题解答

### Q1：我可以在一个日历中添加多个例外吗？

 A1：是的，您可以使用以下命令向日历添加多个例外：`AddRange`方法。

### Q2：如何处理经常出现的例外情况，例如每周假期？

A2：您可以以编程方式计算重复出现的异常，并使用自定义逻辑将它们添加到日历中。

### Q3：是否可以从外部来源导入日历例外？

A3：是的，您可以从数据库或 CSV 文件等外部来源读取日历例外，并将其集成到您的项目中。

### Q4：如果日历中有重叠的例外情况会怎样？

A4：Aspose.Tasks for .NET 允许您根据项目需求定义优先级或解决冲突来处理重叠异常。

### Q5：例外情况下我可以自定义每天的工作时间吗？

A5：是的，您可以在例外情况下为个别日期指定自定义工作时间，以满足特定的日程安排需求。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

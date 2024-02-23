---
title: Aspose.Tasks 中的每日日历重复
linktitle: Aspose.Tasks 中的每日日历重复
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中通过每日日历重复创建重复任务。轻松提高项目管理效率。
type: docs
weight: 25
url: /zh/net/calendar-scheduling/daily-calendar-repetition/
---
## 介绍

 Aspose.Tasks for .NET 提供了一组强大的工具，用于以编程方式管理任务和项目。其显着功能之一是能够有效处理日常日历重复。在本教程中，我们将探讨如何利用`DailyCalendarRepetition`类与其他相关类一起创建基于指定日历每天重复的重复任务。

## 先决条件

在开始之前，请确保您已进行以下设置：

1. 安装：确保您已安装 Aspose.Tasks for .NET。如果没有，您可以从以下位置下载[这里](https://releases.aspose.com/tasks/net/).

2. 命名空间导入：将必要的命名空间导入到您的项目中：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## 第 1 步：初始化项目

首先，我们需要加载现有项目或创建一个新项目来使用：

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 第 2 步：定义日历

接下来，我们创建一个持续时间为 24 小时的日历并将其与项目关联：

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## 步骤 3：设置重复任务参数

现在，让我们为重复任务设置参数。我们定义它的名称、持续时间、重复模式和范围：

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## 步骤 4：设置任务日历

将定义的日历与任务关联：

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## 第 5 步：将任务添加到项目

将具有定义参数的任务添加到项目中：

```csharp
project.RootTask.Children.Add(parameters);
```

## 第 6 步：保存项目

最后，保存添加了重复任务的项目：

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

现在，您已经使用 Aspose.Tasks for .NET 成功创建了一个项目，其中的重复任务设置为基于 24 小时日历每天重复！

## 结论

在本教程中，我们演示了如何利用 Aspose.Tasks for .NET 有效地处理每日日历重复。通过执行这些步骤，您可以将重复任务无缝集成到您的项目中，从而提高生产力和组织性。

## 常见问题解答

### Q1：我可以自定义每次重复的持续时间吗？

A1：是的，您可以根据自己的要求，通过修改代码中的参数来调整每次重复的持续时间。

### Q2：同一项目中的不同任务是否可以设置不同的日历？

A2：当然，Aspose.Tasks 允许您将特定的日历分配给各个任务，从而提供日程安排的灵活性。

### Q3：Aspose.Tasks 是否支持除每日之外的其他重复模式？

A3：是的，Aspose.Tasks 提供了每周、每月、每年等多种重复模式，满足不同的项目需求。

### Q4：我可以可视化使用 Aspose.Tasks 创建的重复任务吗？

A4：当然，Aspose.Tasks 提供可视化选项来帮助您有效地分析和跟踪重复任务。

### Q5：Aspose.Tasks 有试用版吗？

 A5：是的，您可以免费试用 Aspose.Tasks[这里](https://releases.aspose.com/)在购买之前探索其功能。
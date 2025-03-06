---
title: Aspose.Tasks 中按月周日重复
linktitle: Aspose.Tasks 中按月周日重复
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中按月、周和日设置重复，以高效地自动执行重复任务。
type: docs
weight: 26
url: /zh/net/advanced-features/repetition-by-month-week-day/
---
## 介绍

在软件开发领域，特别是在项目管理应用程序中，有效处理重复任务的能力至关重要。 Aspose.Tasks for .NET 是一个功能强大的库，旨在简化项目任务（包括重复任务）的创建和管理。 Aspose.Tasks 提供的其中一项功能是能够按月、周和日设置重复，确保任务按计划执行，无需人工干预。

## 先决条件

在深入研究使用 Aspose.Tasks for .NET 按月、周和日设置重复的复杂性之前，请确保满足以下先决条件：

1. 对 C# 的基本了解：熟悉 C# 编程语言对于理解和实现所提供的代码示例至关重要。
   
2. 安装 Aspose.Tasks for .NET：确保您已下载并安装 Aspose.Tasks for .NET 库。您可以从以下位置获取该库：[下载页面](https://releases.aspose.com/tasks/net/).

3. 访问 .mpp 项目文件：准备好 Microsoft Project 文件 (.mpp)，因为我们将利用它来演示按月、周和日进行重复的实现。

## 导入命名空间

要开始在 C# 应用程序中使用 Aspose.Tasks for .NET，您需要导入必要的命名空间。您可以这样做：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

让我们将提供的代码片段分解为多个步骤，以彻底理解每个部分。

## 第 1 步：加载项目文件

```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

此步骤涉及创建一个新实例`Project`类并加载现有的 Microsoft Project 文件（`Project1.mpp`）从指定的目录。

## 第 2 步：定义重复任务参数

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

在此步骤中，我们定义重复任务的参数。我们指定任务名称、持续时间、重复模式（每月）和重复范围（以特定日期结束）。

## 第 3 步：将重复任务添加到项目中

```csharp
project.RootTask.Children.Add(parameters);
```

在这里，我们将定义的重复任务参数添加到项目的根任务中。

## 第 4 步：保存项目文件

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

最后，我们保存修改后的项目文件以及添加的重复任务。

## 结论

总之，在 Aspose.Tasks for .NET 中按月、周和日设置重复是一个简单的过程，使开发人员能够有效地自动管理项目中的重复任务。通过遵循本教程中概述的步骤，您可以将此功能无缝集成到您的 C# 应用程序中，从而节省项目管理的时间和精力。

## 常见问题解答

###Q1：除了提供的示例之外，我还可以自定义重复模式吗？

A1：是的，Aspose.Tasks for .NET 为重复模式提供了广泛的自定义选项，允许您根据您的特定要求进行定制。

###Q2：Aspose.Tasks for .NET 有试用版吗？

 A2：是的，您可以从 Aspose.Tasks for .NET 获取免费试用版[发布页面](https://releases.aspose.com/).

###Q3：如何获得对 Aspose.Tasks for .NET 的支持？

 A3：您可以寻求帮助并与社区互动[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).

###Q4：Aspose.Tasks for .NET 是否有临时许可证？

 A4：是的，您可以从[购买页面](https://purchase.aspose.com/temporary-license/)用于测试和评估目的。

###Q5：在哪里可以找到 Aspose.Tasks for .NET 的综合文档？

 A5：您可以参考详细的[文档](https://reference.aspose.com/tasks/net/)可在 Aspose 网站上获取有关使用该库的深入指导。
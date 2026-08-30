---
date: 2026-04-01
description: 学习如何在 Aspose.Tasks for .NET 中设置循环，添加循环任务，并按月、周、日自动化循环任务。
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Aspose.Tasks 中的按月、周、日重复
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中设置循环（按月、按周、按天）
url: /zh/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中设置重复（月份、星期、天）

## 介绍

如果您需要为项目中的任务**设置重复**，Aspose.Tasks for .NET 提供了一种简洁的编程方式来添加按月、按周或按天运行的重复任务定义。在本教程中，我们将通过一个真实案例演示如何**添加重复任务**条目、**自动化重复任务**，以及如何直接从 C# 代码中管理它们。完成后，您即可将此功能集成到任何调度或项目管理解决方案中。

## 快速答案
- **“recurrence” 在 Aspose.Tasks 中是什么意思？** 它定义了一种模式（每日、每周、每月），在日期范围内自动创建任务实例。  
- **哪个主要方法创建重复？** `RecurringTaskParameters` 与特定的 `RecurrencePattern` 结合使用。  
- **运行此代码是否需要许可证？** 试用版可用于评估；生产环境需要商业许可证。  
- **我可以安排每周任务而不是每月任务吗？** 是的 – 将 `MonthlyRecurrencePattern` 替换为 `WeeklyRecurrencePattern`。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6 及更高版本。

## Aspose.Tasks 中的重复是什么？

重复是一组规则，指示 Aspose.Tasks 在固定间隔（每日、每周或每月）生成任务实例，而无需手动复制它们。此功能对于包含例行活动（如状态会议、检查或维护工作）的项目至关重要。

## 为什么使用重复功能？

- **节省时间：** 无需手动复制粘贴任务。  
- **减少错误：** 该库确保日期和持续时间的一致性。  
- **灵活性：** 组合模式（例如，“每 2 个月的第一个星期日”）。  
- **自动化：** 适用于在 CI 流水线或报告工具中生成计划。

## 先决条件

在开始之前，请确保您具备以下条件：

1. **C# 基础知识** – 您将编写几行 C# 代码。  
2. **已安装 Aspose.Tasks for .NET** – 从[下载页面](https://releases.aspose.com/tasks/net/)获取。  
3. **一个 .mpp 项目文件** – 我们将使用 `Project1.mpp` 作为源文件。

## 导入命名空间

首先，导入所需的 Aspose.Tasks 命名空间：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 步骤 1：加载项目文件

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

我们创建一个指向现有 Microsoft Project 文件的 `Project` 实例。

### 步骤 2：定义重复任务参数

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

这里我们**创建重复任务**参数：

- **TaskName** – 生成任务的名称。  
- **Duration** – 每次出现的持续时间。  
- **RecurrencePattern** – 每 2 个月的第一个星期日重复的月度模式。  
- **RecurrenceRange** – 界定计划的开始和结束日期。

### 步骤 3：将重复任务添加到项目中

```csharp
project.RootTask.Children.Add(parameters);
```

此行**将重复任务**添加到项目层级的根节点。

### 步骤 4：保存更新后的项目

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

项目将保存为一个新的 `.mpp` 文件，其中已包含自动化的计划。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **任务未出现** | 重复范围超出项目日期。 | 确认 `Start` 和 `Finish` 值在项目日历范围内。 |
| **星期几错误** | `WeekDay` 枚举不匹配。 | 根据需要使用 `DayOfWeek.Monday` … `DayOfWeek.Sunday`。 |
| **许可证异常** | 在生产环境中未使用有效许可证运行。 | 在保存前应用临时或完整许可证。 |

## 常见问题

### Q1：我可以自定义重复模式，而不仅限于提供的示例吗？

A1: 是的，Aspose.Tasks for .NET 提供了广泛的重复模式自定义选项，允许您根据具体需求进行调整。

### Q2：Aspose.Tasks for .NET 有试用版吗？

A2: 是的，您可以从[发布页面](https://releases.aspose.com/)获取 Aspose.Tasks for .NET 的免费试用版。

### Q3：我如何获取 Aspose.Tasks for .NET 的支持？

A3: 您可以在[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)上寻求帮助并与社区互动。

### Q4：Aspose.Tasks for .NET 有临时许可证吗？

A4: 是的，您可以从[购买页面](https://purchase.aspose.com/temporary-license/)获取临时许可证，用于测试和评估目的。

### Q5：在哪里可以找到 Aspose.Tasks for .NET 的完整文档？

A5: 您可以参考 Aspose 网站上提供的详细[文档](https://reference.aspose.com/tasks/net/)，获取关于使用该库的深入指导。

---

**最后更新：** 2026-04-01  
**测试环境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
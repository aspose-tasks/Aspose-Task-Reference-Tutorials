---
date: 2026-03-08
description: 通过本分步教程，学习如何在 Aspose.Tasks for .NET 中创建每月循环任务。
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中创建每月重复任务
url: /zh/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 创建月度循环任务

## 介绍

Aspose.Tasks for .NET 让您能够以编程方式操作 Microsoft Project 文件，最常见的实际需求之一是**创建月度循环任务**计划。无论您是构建项目跟踪工具、自动化资源分配，还是生成循环维护工作项，本教程都会逐步演示如何向任务添加月度重复模式。

在接下来的章节中，您将看到如何设置项目、定义重复参数，最后保存更新后的文件——全部配有清晰的解释和实用技巧。

## 快速答案
- **What does “monthly recurring task” mean?** 每月按照定义的日或周模式重复的任务。  
- **Which API class handles recurrence?** `RecurringTaskParameters` 与 `MonthlyRecurrencePattern` 一起处理。  
- **Do I need a license to run the sample?** 免费试用可用于评估；生产环境需要许可证。  
- **Can I change the interval?** 可以——将 `RepetitionInterval` 设置为两次出现之间的月份数。  
- **What file formats are supported?** `.mpp` 和 `.xml` 项目文件均可加载和保存。

## 什么是月度重复模式？

月度重复模式告诉 Microsoft Project（以及 Aspose.Tasks）任务每月应重复的频率。您可以指定月份的固定日期（例如第 1 天）或相对位置（例如最后一个星期五）。API 会将这些规则转换为底层的 Project 文件结构。

## 为什么使用 Aspose.Tasks？

- **Full control** – 无 UI 限制；您可以在代码中定义模式的每个细节。  
- **Cross‑platform** – 可在 .NET Framework、.NET Core 和 .NET 5/6+ 上运行。  
- **No Microsoft Project required** – 可在服务器或 CI 流水线中生成或修改文件。

## 前提条件

在开始之前，请确保您已具备：

- 已安装 .NET 6（或 .NET 5/Framework 4.7+）。  
- 已在项目中添加 Aspose.Tasks for .NET NuGet 包。  
- 将示例项目文件 (`Project1.mpp`) 放置在已知文件夹 (`DataDir`) 中。

## 导入命名空间

首先，导入处理任务和保存项目所需的命名空间：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## 步骤 1：初始化项目

创建指向现有 `.mpp` 文件的 `Project` 实例。该实例会将文件加载到内存，以便您进行修改。

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Pro tip:** 如果文件不存在，Aspose.Tasks 将自动创建一个新的空白项目。

## 步骤 2：设置循环任务参数

定义循环任务的详细信息，包括名称、持续时间以及要应用的月度模式。

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1` 表示任务在每月的**第一天**发生。  
- `RepetitionInterval = 2` 使任务每**两个月**重复一次。  
- `Start` 和 `Finish` 定义了重复模式生效的整体时间窗口。

## 步骤 3：将参数添加到项目中

将 `RecurringTaskParameters` 对象附加到根任务的子集合中。这实际上在项目层次结构中创建了循环任务。

```csharp
project.RootTask.Children.Add(parameters);
```

## 步骤 4：保存项目

通过将项目保存为新文件来持久化更改。您可以选择任何受支持的格式；此处使用原生 `.mpp` 格式。

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

运行代码后，在 Microsoft Project 中打开生成的文件，即可看到您刚创建的月度循环任务。

## 常见问题及解决方案

| Issue | Cause | Fix |
|-------|-------|-----|
| 保存后任务未出现 | UI 中项目未刷新 | 重新打开文件或在保存前调用 `project.UpdateTaskLinks()`。 |
| 开始日期错误 | `Start` 设置为周末 | 使用落在工作日的 `DateTime`，或调整日历。 |
| 重复间隔被忽略 | 使用 `ByMonthDayRepetition` 且 `DayPosition` = 0 | 确保 `DayPosition` 为 1‑31。 |

## 结论

通过遵循这些步骤，您现在了解如何使用 Aspose.Tasks for .NET **创建月度循环任务**计划。API 为您提供对重复间隔、开始/结束范围以及具体日期模式的细粒度控制，使您能够自动化复杂的项目规划场景。

## 常见问答

### Q1: Aspose.Tasks 是否兼容所有版本的 Microsoft Project 文件？

A1: Aspose.Tasks 支持多种版本的 Microsoft Project 文件，包括 MPP、MPT、XML 和 MPX。

### Q2: 我可以进一步自定义重复模式吗？

A2: 可以，Aspose.Tasks 提供了丰富的选项来自定义重复模式，包括每日、每周、每月和每年。

### Q3: 是否提供 Aspose.Tasks 的免费试用？

A3: 是的，您可以从网站 [here](https://releases.aspose.com/) 获取 Aspose.Tasks 的免费试用。

### Q4: 如何获取 Aspose.Tasks 的支持？

A4: 您可以在 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 上寻求帮助并参与讨论。

### Q5: 在哪里可以购买 Aspose.Tasks 的许可证？

A5: 您可以在网站 [here](https://purchase.aspose.com/buy) 购买 Aspose.Tasks 的许可证。

## 常见问题

**Q: 我可以在 .NET Core 应用程序中使用此代码吗？**  
A: 当然可以。Aspose.Tasks for .NET 完全支持 .NET Core 3.1 及更高版本。

**Q: 如何将重复改为“本月最后一个工作日”？**  
A: 使用 `ByMonthDayRepetition` 并将 `DayPosition = -1`（负值表示从月份末计数），并相应设置 `WeekDay`。

**Q: 如果重复范围超出项目日历会怎样？**  
A: API 会遵循项目日历；落在非工作日的出现要么被跳过，要么根据日历设置进行移动。

**Q: 能否删除循环任务的特定出现吗？**  
A: 可以。添加循环任务后，您可以通过 `Task.GetOccurrences()` 获取各个出现并删除不需要的。

**Q: Aspose.Tasks 是否会自动处理时区差异？**  
A: 该库以 UTC 存储日期；如有需要，您可以使用标准 .NET `DateTime` 方法转换为本地时间。

---

**最后更新:** 2026-03-08  
**测试环境:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-04-03
description: 学习项目管理任务调度以及如何使用 Aspose.Tasks for .NET 添加循环任务，包括将项目保存为 MPP。
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Aspose.Tasks 中的按年天重复
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 中实现按年天重复的项目管理任务调度
url: /zh/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中按年日重复的项目管理任务调度

## 介绍

Effective **project management task scheduling** 是任何成功项目的基石。当任务以年度方式重复——例如年度审计、维护窗口或季节性评审——手动处理这些重复会容易出错且耗时。Aspose.Tasks for .NET 通过让您以编程方式定义年日模式来简化此过程，从而让您专注于最重要的事情：交付价值。在本教程中，您将学习 **how to add recurring task** 逻辑，并准确了解 **how to save project as MPP**，以实现与 Microsoft Project 的无缝集成。

## 快速答案
- **What does “year day repetition” mean?** 它在每年的特定月份的特定日期安排任务。  
- **Which API class creates the recurrence?** `YearlyRecurrencePattern` 与 `ByYearDayRepetition` 组合使用。  
- **Can I set a start and end date?** 可以，使用 `EndByRecurrenceRange`。  
- **What file format is produced?** 项目保存为 MPP 文件（`SaveFileFormat.Mpp`）。  
- **Do I need a license for production?** 对于非评估使用，需要商业许可证。

## 前提条件

在深入教程之前，请确保您已具备以下前提条件：

1. Aspose.Tasks for .NET 库：从[website](https://releases.aspose.com/tasks/net/)下载并安装 Aspose.Tasks for .NET 库。  
2. 开发环境：使用 Visual Studio 或其他您偏好的 .NET 开发 IDE，搭建合适的开发环境。  
3. C# 基础知识：熟悉 C# 编程语言的基础，以便跟随代码示例。  
4. 项目管理概念：了解项目管理概念和任务调度，有助于有效掌握本教程的内容。

## 导入命名空间

在开始编写代码之前，让我们导入必要的命名空间，以便使用 Aspose.Tasks for .NET 进行任务操作。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

现在，让我们将提供的示例拆分为多个步骤，并详细阐述每一步。

## 如何使用年日模式添加循环任务

### 步骤 1：加载项目文件

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

这里，我们初始化一个新的 `Project` 对象，并加载名为 **Project1.mpp** 的现有项目文件。

### 步骤 2：定义循环任务参数

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

在此步骤中，我们为循环任务定义参数。我们指定任务名称、持续时间和循环模式。对于年度循环，我们使用 `YearlyRecurrencePattern` 并通过 `ByYearDayRepetition` 将重复设置为 **7 月 1 日**。此外，我们将循环范围定义为 2018 年 7 月 1 日至 2019 年 7 月 1 日。

### 步骤 3：将任务添加到项目中

```csharp
project.RootTask.Children.Add(parameters);
```

这里，我们将已定义的循环任务参数添加到项目的根任务中。

### 步骤 4：将项目保存为 MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

最后，我们 **将项目保存为 MPP 文件**，使其可以在 Microsoft Project 或任何兼容的查看器中打开。

## 为什么这很重要

- **Automation** – 消除对年度任务的手动输入，降低人为错误。  
- **Consistency** – 确保在多个年份中应用相同的日‑月模式。  
- **Integration** – 生成的 MPP 文件可与依赖 Microsoft Project 的利益相关者共享。

## 常见陷阱与技巧

- **DateTime precision** – 确保开始时间与项目日历对齐；否则任务可能出现偏移。  
- **Time zones** – API 使用 `DateTime` 对象；如果您的应用跨多个地区，请考虑 UTC 转换。  
- **License enforcement** – 在评估模式下，保存的 MPP 可能包含水印；生产环境请使用有效许可证。

## 常见问题

**Q: Aspose.Tasks 能处理复杂的循环模式吗？**  
A: 可以，Aspose.Tasks 提供对各种循环模式的全面支持，包括年度、月度、每周和每日重复。

**Q: Aspose.Tasks 是否兼容不同的项目文件格式？**  
A: 绝对兼容，Aspose.Tasks 支持常见的项目文件格式，如 MPP、XML 和 CSV，确保在不同项目管理工具之间的兼容性。

**Q: Aspose.Tasks 为开发者提供文档和支持吗？**  
A: 是的，开发者可以访问丰富的文档，并在 Aspose.Tasks 社区论坛寻求帮助，解决任何疑问或问题。

**Q: 我可以使用 Aspose.Tasks 自定义任务属性，如持续时间和开始日期吗？**  
A: 当然，Aspose.Tasks 提供强大的 API 来动态操作任务属性，允许开发者自定义持续时间、开始日期、依赖关系等。

**Q: Aspose.Tasks 适用于小规模和企业级项目吗？**  
A: 确实，Aspose.Tasks 旨在满足各种规模项目的开发者需求，从单个任务到大型企业项目皆可使用。

---

**最后更新:** 2026-04-03  
**测试环境:** Aspose.Tasks 24.12 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
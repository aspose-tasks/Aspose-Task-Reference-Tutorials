---
date: 2026-04-03
description: 学习如何使用 Aspose.Tasks 添加循环任务项目并将项目保存为 MPP。本指南逐步展示了按年、周、日的重复功能。
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Aspose.Tasks 中的按年、周、日重复
second_title: Aspose.Tasks .NET API
title: 如何使用 Aspose.Tasks – 按年、周、日重复
url: /zh/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的按年周日重复

## 介绍

当您需要 **how to use Aspose.Tasks** 来处理复杂的循环计划时，库提供了对年度模式的细粒度控制。在本教程中，我们将演示如何创建一个在特定月份的特定星期几重复的任务，跨越多个年份。完成后，您将能够使用几行 C# 代码 **add recurring task project** 条目并 **save project as MPP**。

## 快速回答
- **“Repetition by Year Week Day” 是什么意思？** 它在每年指定月份的选定星期几（例如第一个星期日）重复任务。  
- **支持哪些 .NET 版本？** 支持所有现代 .NET Framework 和 .NET Core/5/6 版本。  
- **运行代码是否需要许可证？** 开发阶段可使用免费试用版；生产环境需要商业许可证。  
- **我可以更改重复范围吗？** 可以——您可以设置开始日期、结束日期或固定的出现次数。  
- **输出是 MPP 文件吗？** 完全是——项目会保存为可在 Microsoft Project 中打开的 MPP 文件。

## 什么是“按年周日重复”功能？

该功能允许您定义一个年度循环，针对特定的 **day of the week**（如 Sunday）以及 **position**（月份中的第一、第二、最后等）。这非常适合季度评审、年度审计或任何基于日历节奏的事件。

## 为什么在循环任务中使用 Aspose.Tasks？

- **Precision** – 完全控制月份、星期几和序数位置。  
- **Compatibility** – 生成本机 MPP 文件，可在 Microsoft Project 中无缝打开。  
- **No COM interop** – 纯 .NET API，无需安装 Office。  
- **Scalability** – 适用于小型项目和企业级计划。

## 前置条件

在深入代码之前，请确保您具备：

1. **Basic .NET knowledge** – 熟悉 C# 和面向对象概念。  
2. **Aspose.Tasks for .NET** – 从 [download link](https://releases.aspose.com/tasks/net/) 下载并将 DLL 添加到项目中。  
3. **Access to the official docs** – [documentation](https://reference.aspose.com/tasks/net/) 包含所有类的详细信息。  
4. **A development IDE** – Visual Studio、Rider 或任何兼容的 .NET 编辑器。

准备就绪后，让我们看看实现方式。

## 如何使用 Aspose.Tasks 进行循环任务

### 导入必要的命名空间

首先，引入所需的命名空间，以便能够操作项目、任务和保存选项。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 步骤 1：初始化项目和任务参数

创建一个新的 `Project` 实例，然后定义一个描述循环模式的 `RecurringTaskParameters` 对象。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** 调整 `Month`、`WeekDay` 和 `Position` 以匹配您的实际日程安排。

### 步骤 2：将参数添加到项目

将循环任务定义插入项目的根节点。

```csharp
project.RootTask.Children.Add(parameters);
```

### 步骤 3：将项目保存为 MPP

最后，将项目持久化为 MPP 文件，以便在 Microsoft Project 或任何兼容的查看器中打开。

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> 这演示了在一行代码中 **save project as mpp**。

## 常见问题及解决方案

| 症状 | 可能原因 | 解决办法 |
|---------|--------------|-----|
| 打开 MPP 文件后没有任务显示 | 重复范围日期超出项目日历 | 确认 `Start` 和 `Finish` 日期在项目的工作时间范围内 |
| 在 `Add` 时抛出 `ArgumentNullException` | `parameters` 为 null 或未完全初始化 | 确保已设置所有必需属性（TaskName、Duration、RecurrencePattern） |
| 选择了错误的星期几 | `WeekDay` 枚举值不匹配 | 根据需要使用 `DayOfWeek.Monday` … `DayOfWeek.Sunday` |

## 常见问答

**Q: 我可以自定义除示例之外的重复模式吗？**  
**A:** 是的，Aspose.Tasks 允许您组合 `MonthlyRecurrencePattern`、`WeeklyRecurrencePattern` 或甚至自定义 `RecurrenceRange` 对象以适应任何计划。

**Q: Aspose.Tasks for .NET 与其他项目管理软件兼容吗？**  
**A:** 完全兼容——库能够读取和写入 MPP、XML 和 Primavera 格式，实现平滑的数据交换。

**Q: 我该如何处理循环任务的异常或修改？**  
**A:** 使用 `ExceptionTask` 类为特定出现创建覆盖，或编辑 `RecurringTaskParameters` 并重新保存项目。

**Q: Aspose.Tasks 支持云端解决方案吗？**  
**A:** 支持——您可以在 Azure Functions、AWS Lambda 或任何兼容 .NET 的云服务中运行该 API。

**Q: 是否有 Aspose.Tasks for .NET 的试用版？**  
**A:** 有，您可以从 [website](https://releases.aspose.com/) 获取 Aspose.Tasks for .NET 的免费试用版，以在购买前评估其功能。

**Q: 如何在不覆盖其他数据的情况下向现有项目添加循环任务？**  
**A:** 使用 `new Project("Existing.mpp")` 加载现有项目，将 `RecurringTaskParameters` 添加到 `RootTask.Children`，然后 `Save` 文件。

## 结论

通过掌握 **how to use Aspose.Tasks** 在 **Repetition by Year Week Day** 场景下的使用，您能够 **add recurring task project** 条目，使其完美契合真实日历，并 **save project as MPP** 以实现无缝协作。将这些代码片段整合到您的解决方案中，可提升排程准确性并减少手动工作量。

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
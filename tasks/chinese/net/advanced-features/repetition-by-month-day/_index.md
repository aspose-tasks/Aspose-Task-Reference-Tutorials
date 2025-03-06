---
title: Aspose.Tasks 中按月日重复
linktitle: Aspose.Tasks 中按月日重复
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 管理 .NET 项目中的重复任务。按月日处理重复的分步指南。
weight: 25
url: /zh/net/advanced-features/repetition-by-month-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中按月日重复

## 介绍

在.NET 开发领域，Aspose.Tasks 是管理项目任务和进度的强大工具。它提供了大量的功能来简化项目管理工作流程，包括处理重复任务。按月日重复是项目调度中的常见要求，Aspose.Tasks 为这种情况提供了强大的支持。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

1. 对 C# 的基本了解：要掌握本教程中讨论的概念，需要熟悉 C# 编程语言。
2. 安装Aspose.Tasks for .NET：确保您已经安装了Aspose.Tasks for .NET。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/net/).
3. 集成开发环境 (IDE)：在系统上安装 Visual Studio 等 IDE，以方便编码。

## 导入命名空间

在您的 C# 项目中，导入必要的命名空间以访问 Aspose.Tasks 功能：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

让我们将提供的代码示例分解为分步指南格式：

## 第 1 步：加载项目文件

```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

这行代码初始化了一个新的实例`Project`类，加载名为“Project1.mpp”的项目文件。

## 第 2 步：定义重复任务参数

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

此部分定义重复任务的参数，包括其名称、持续时间、重复模式和重复范围。

## 第 3 步：将任务添加到项目中

```csharp
project.RootTask.Children.Add(parameters);
```

在这里，我们将重复任务参数添加到项目中。

## 第 4 步：保存项目文件

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

最后，修改后的项目与添加的重复任务一起保存。

## 结论

在本教程中，我们探讨了如何在 Aspose.Tasks for .NET 中按月处理重复。通过遵循提供的步骤，您可以有效地管理项目计划中的重复任务。

## 常见问题解答

### Q1：Aspose.Tasks 是否与所有版本的.NET 兼容？

A1：Aspose.Tasks支持各种版本的.NET框架，确保不同环境下的兼容性。

### Q2：我可以进一步自定义重复模式吗？

A2：是的，Aspose.Tasks 提供了广泛的自定义选项，用于根据特定项目要求定义重复模式。

### Q3：Aspose.Tasks 是否提供对其他项目管理功能的支持？

A3：当然，Aspose.Tasks 为项目管理提供了广泛的功能，包括任务跟踪、资源分配和甘特图生成。

### Q4：Aspose.Tasks 有试用版吗？

 A4：是的，您可以免费试用[这里](https://releases.aspose.com/)在做出购买决定之前探索 Aspose.Tasks 的功能。

### Q5：如果我遇到问题或有疑问，可以到哪里寻求帮助？

 A5：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)寻求社区或 Aspose 团队的支持。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

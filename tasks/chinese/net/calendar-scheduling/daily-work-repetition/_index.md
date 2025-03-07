---
title: Aspose.Tasks 中的日常工作重复
linktitle: Aspose.Tasks 中的日常工作重复
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 Microsoft Project 文件中创建每日重复任务。轻松提高生产力和组织能力。
weight: 26
url: /zh/net/calendar-scheduling/daily-work-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的日常工作重复

## 介绍

Aspose.Tasks for .NET 是一个功能强大的库，使开发人员能够轻松操作 Microsoft Project 文件。其众多功能之一是能够有效处理重复任务。在本教程中，我们将深入研究日常工作重复功能，该功能允许创建在项目中每天重复的任务。

## 先决条件

在深入学习本教程之前，请确保您具备以下条件：

- C# 和 .NET 框架的基础知识。
- Visual Studio 安装在您的系统上。
-  .NET 库的 Aspose.Tasks。你可以下载它[这里](https://releases.aspose.com/tasks/net/).
- 熟悉 Microsoft Project 文件 (.mpp)。

## 导入命名空间

在开始之前，请确保导入必要的命名空间：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

让我们将提供的示例分解为多个步骤：

## 第 1 步：加载项目文件

首先，使用以下命令加载项目文件`Project`班级：

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 第 2 步：定义重复任务参数

定义重复任务的参数：

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## 步骤 3：设置日历和任务开始日期

设置任务的日历和开始日期：

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## 结论

在本教程中，我们探讨了如何利用 Aspose.Tasks for .NET 创建具有日常重复工作的重复任务。通过执行这些步骤，您可以有效地管理项目中的任务，确保工作流程和组织顺利进行。

## 常见问题解答

### Q1：我可以进一步自定义重复模式吗？

A1：是的，您可以调整开始日期、发生次数和重复间隔等参数，以根据您的要求定制重复模式。

### Q2：Aspose.Tasks 是否与不同版本的 Microsoft Project 兼容？

A2：是的，Aspose.Tasks支持各种版本的Microsoft Project，确保兼容性和无缝集成。

### Q3：如何处理重复任务的异常或修改？

A3：Aspose.Tasks 提供了强大的功能来管理重复任务中的异常和修改，从而实现灵活性和自定义。

### Q4: 我可以将项目导出为不同的格式吗？

A4：当然，Aspose.Tasks 支持将项目导出为各种格式，包括 PDF、HTML、XML 等，方便共享和协作。

### Q5：Aspose.Tasks 提供技术支持吗？

A5：是的，Aspose.Tasks 通过其论坛提供全面的技术支持，您可以在其中寻求帮助、分享经验并与其他用户互动。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

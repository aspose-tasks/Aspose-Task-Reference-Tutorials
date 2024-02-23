---
title: 在 Aspose.Tasks 中处理每月重复模式
linktitle: 在 Aspose.Tasks 中处理每月重复模式
second_title: Aspose.Tasks .NET API
description: 通过此分步教程，了解如何在 Aspose.Tasks for .NET 中处理每月重复模式。
type: docs
weight: 18
url: /zh/net/advanced-concepts/monthly-recurrence-patterns/
---
## 介绍

Aspose.Tasks for .NET 是一个功能强大的 API，允许开发人员以编程方式操作 Microsoft Project 文件。它提供的基本功能之一是能够有效处理重复任务。在本教程中，我们将逐步深入研究如何使用 Aspose.Tasks 处理每月重复模式。

## 先决条件

在开始之前，请确保您已安装以下先决条件：

## 导入命名空间

首先，确保您已在 .NET 项目中导入了必要的命名空间：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

现在，让我们将处理每月重复模式的过程分解为多个步骤：

## 第 1 步：初始化项目

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 步骤 2：设置重复任务参数

定义重复任务的参数，包括任务名称、持续时间和重复模式：

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

## 第3步：向项目添加参数

```csharp
project.RootTask.Children.Add(parameters);
```

## 第 4 步：保存项目

使用重复任务保存修改后的项目：

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## 结论

在 Aspose.Tasks for .NET 中处理每月重复模式既简单又高效。通过遵循本教程中概述的步骤，您可以轻松创建具有特定每月间隔和重复范围的重复任务。

## 常见问题解答

### Q1：Aspose.Tasks 是否与所有版本的 Microsoft Project 文件兼容？

A1：Aspose.Tasks支持各种版本的Microsoft Project文件，包括MPP、MPT、XML和MPX。

### Q2：我可以进一步自定义重复模式吗？

A2：是的，Aspose.Tasks 提供了广泛的选项用于自定义重复模式，包括每日、每周、每月和每年。

### Q3：Aspose.Tasks 有免费试用版吗？

 A3：是的，您可以从网站获得Aspose.Tasks的免费试用版[这里](https://releases.aspose.com/).

### Q4：如何获得 Aspose.Tasks 的支持？

 A4：您可以寻求帮助并参与讨论[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).

### Q5：在哪里可以购买 Aspose.Tasks 的许可证？

 A5：您可以从网站购买Aspose.Tasks的许可证[这里](https://purchase.aspose.com/buy)
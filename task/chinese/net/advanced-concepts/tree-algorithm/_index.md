---
title: 在 Aspose.Tasks 中使用树算法
linktitle: 在 Aspose.Tasks 中使用树算法
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 的树算法有效地操作 .NET 项目中的任务层次结构。
type: docs
weight: 13
url: /zh/net/advanced-concepts/tree-algorithm/
---
## 介绍

Aspose.Tasks for .NET 提供了强大的功能来处理项目管理任务、资源和时间表。其中一项功能是树算法，它允许用户有效地操作任务层次结构。在本教程中，我们将探索如何利用 Aspose.Tasks for .NET 中的树算法来收集项目中的常见工作并更新工作值。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

1. Visual Studio：确保您的系统上安装了 Visual Studio。
2.  Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET[这里](https://releases.aspose.com/tasks/net/).
3. 对 C# 的基本了解：需要熟悉 C# 编程语言才能跟随示例。

## 导入命名空间

在您的 C# 项目中，导入必要的命名空间以使用 Aspose.Tasks 功能：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

现在，让我们将每个示例分解为多个步骤：

## 第 1 步：加载项目文件

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

使用以下命令将项目文件加载到内存中`Project`班级。

## 第 2 步：定义任务层次结构

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

通过添加父任务和子任务来定义任务层次结构。

## 步骤 3：设置任务属性

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

设置任务的开始日期、持续时间和完成日期等属性。

## 第四步：添加资源

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

将资源添加到项目中并根据需要将其分配给任务。

## 第5步：应用树算法

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

初始化`WorkAccumulator`类并应用树算法来收集共同的工作。

## 第 6 步：更新任务工作

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

根据收集的信息更新任务的工作值。

## 结论

在本教程中，我们学习了如何利用 Aspose.Tasks for .NET 中的树算法来有效地操作任务层次结构。通过遵循分步指南，您可以有效地管理项目中的任务和资源。

## 常见问题解答

### Q1：什么是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一个功能强大的 API，允许开发人员使用 C# 以编程方式操作 Microsoft Project 文件。

### 问题 2：我可以下载 Aspose.Tasks for .NET 的免费试用版吗？

 A2：是的，您可以从以下位置下载 Aspose.Tasks for .NET 的免费试用版：[这里](https://releases.aspose.com/).

### Q3：在哪里可以找到 Aspose.Tasks for .NET 的文档？

 A3：您可以找到 Aspose.Tasks for .NET 的文档[这里](https://reference.aspose.com/tasks/net/).

### Q4：如何获得 Aspose.Tasks for .NET 支持？

 A4：有关 Aspose.Tasks for .NET 的支持，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).

### Q5：是否有可用于测试目的的临时许可证？

 A5：是的，您可以从以下位置获取用于测试目的的临时许可证：[这里](https://purchase.aspose.com/temporary-license/).
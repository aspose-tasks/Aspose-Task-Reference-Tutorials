---
title: 在 Aspose.Tasks 中使用分配
linktitle: 在 Aspose.Tasks 中使用分配
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 管理 .NET 中的项目分配。探索资源调度的不同轮廓。
weight: 13
url: /zh/net/advanced-features/working-with-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中使用分配

## 介绍

在本教程中，我们将探讨如何在 Aspose.Tasks for .NET 中处理作业。分配在项目管理中至关重要，因为它们为任务分配资源，有助于安排和跟踪进度。我们将重点使用 Aspose.Tasks 生成具有各种轮廓的资源分配时间分段数据。

## 先决条件

在我们开始之前，请确保您满足以下先决条件：

1. 安装 Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET 库：[下载链接](https://releases.aspose.com/tasks/net/).
2. 对 C# 和 .NET Framework 的基本了解：需要熟悉 C# 编程语言和 .NET 框架概念才能遵循。

## 导入命名空间

确保将必要的命名空间导入到您的 C# 项目中：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## 第 1 步：创建项目和任务

让我们首先创建一个新项目并向其中添加一个任务。设置任务的开始日期、持续时间和完成日期：

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## 步骤 2：添加资源并分配给任务

接下来，将资源添加到项目并将其分配给之前创建的任务：

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## 步骤 3：生成具有不同轮廓的时间分段数据

现在，让我们为资源分配生成具有不同轮廓的时间分段数据：

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## 第 4 步：更改轮廓并生成数据

我们可以更改等值线类型并相应地生成时间分段数据。这里有些例子：

```csharp
//改变轮廓
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
//生成时间分段数据并打印
//对其他轮廓类型重复此步骤
```

## 结论

在本教程中，我们学习了如何在 Aspose.Tasks for .NET 中处理作业。我们探索了生成具有各种轮廓的资源分配时间分段数据。这些知识在项目管理场景中非常有用。

## 常见问题解答

### Q1：我可以使用 Aspose.Tasks 在我的 .NET 应用程序中安排任务吗？

A1：是的，Aspose.Tasks 为 .NET 应用程序中的任务调度和管理提供了全面的 API。

### Q2：Aspose.Tasks 有免费试用版吗？

 A2：是的，您可以免费试用[这里](https://releases.aspose.com/).

### Q3：Aspose.Tasks 中的任务或资源数量有限制吗？

A3：Aspose.Tasks 不会对您可以在项目中管理的任务或资源的数量施加任何限制。

### Q4：我可以在Aspose.Tasks中自定义资源分配的轮廓吗？

A4: 是的，正如本教程中演示的，您可以根据您的项目要求设置各种轮廓，如海龟、钟形、峰值等。

### Q5：在哪里可以找到对 Aspose.Tasks 相关查询的支持？

A5：您可以在[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)专家和社区成员积极参与讨论。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
date: 2026-03-19
description: 学习如何向项目添加资源并使用 Aspose.Tasks 的树算法计算任务持续时间，以及在 .NET 中将资源分配给任务。
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 使用树形算法在 Aspose.Tasks 中向项目添加资源
url: /zh/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 中的树算法向项目添加资源

## 介绍

在本教程中，您将通过利用 Aspose.Tasks for .NET 提供的强大树算法，了解 **如何向项目添加资源**。我们将逐步演示创建任务层次结构、计算任务持续时间以及将资源分配给任务的过程——所有步骤都清晰明了，您可以直接复制到自己的解决方案中。

## 快速回答
- **Tree Algorithm 的作用是什么？** 它遍历任务层次结构，以高效地聚合工作量值。  
- **本指南主要覆盖的操作是什么？** 向项目添加资源并更新工作总计。  
- **我需要许可证吗？** 生产使用时需要临时许可证或正式许可证。  
- **我可以在 .NET Core 上使用吗？** 可以，Aspose.Tasks 支持 .NET Framework 和 .NET Core。  
- **实现大约需要多长时间？** 对于基本的项目文件，大约需要 10‑15 分钟。

## 在 Aspose.Tasks 中“向项目添加资源”是什么？

向项目添加资源是指创建一个 `Resource` 对象，定义其类型（例如，工作），并通过 `ResourceAssignments` 将其链接到一个或多个任务。这使调度器能够计算工作量、成本以及整个项目的持续时间。

## 为什么在资源工作计算中使用树算法？

树算法只遍历一次任务树，将工作量从叶子任务累计到其汇总任务。这种方法比对每个任务单独迭代要高效得多，尤其是在层次结构深且规模大的项目中。它还能确保汇总工作值与子任务保持同步。

## 前置条件

1. **Visual Studio** – 任意近期版本（2019、2022 或更高）。  
2. **Aspose.Tasks for .NET** – 从 [here](https://releases.aspose.com/tasks/net/) 下载。  
3. **基本的 C# 知识** – 您应熟悉类、对象以及简单的 LINQ。

## 导入命名空间

在您的 C# 项目中，导入必要的命名空间以使用 Aspose.Tasks 功能：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

现在，让我们将每个示例拆分为多个步骤：

## 步骤 1：加载项目文件

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

使用 `Project` 类将项目文件加载到内存中。

## 步骤 2：定义任务层次结构

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

通过添加父任务和子任务来定义任务层次结构。

## 步骤 3：设置任务属性（包括 **计算任务持续时间**）

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

这里我们通过将工作小时转换为 `Duration` 对象来 **计算任务持续时间**，随后得出完成日期。

## 步骤 4：添加资源（**将资源分配给任务**）

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

此代码段 **向项目添加资源** 并 **将资源分配给任务**，使调度器知道谁负责该工作。

## 步骤 5：应用树算法

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

初始化 `WorkAccumulator` 类并应用树算法，以收集层次结构中的公共工作量。

## 步骤 6：更新任务工作量

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

根据收集的信息更新任务的工作量值。

## 常见问题与技巧

- **缺少日历设置：** 如果完成日期不正确，请在调用 `GetFinishDateByStartAndWork` 之前确保项目日历已正确配置。  
- **资源类型不匹配：** 对于基于工作量的资源，始终将 `Rsc.Type` 设置为 `ResourceType.Work`；否则，工作累计可能为零。  
- **专业提示：** 更新工作后，调用 `project.Save("UpdatedProject.mpp")` 以保存更改。

## 结论

通过遵循这些步骤，您现在了解如何使用 Aspose.Tasks 的树算法 **向项目添加资源**、**计算任务持续时间**以及 **将资源分配给任务**。此方法简化了层次结构管理，并以最少的代码保持汇总工作值的准确性。

## 常见问题

### Q1：什么是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一个强大的 API，允许开发者使用 C# 以编程方式操作 Microsoft Project 文件。

### Q2：我可以下载 Aspose.Tasks for .NET 的免费试用吗？

A2：是的，您可以从 [here](https://releases.aspose.com/) 下载 Aspose.Tasks for .NET 的免费试用版。

### Q3：在哪里可以找到 Aspose.Tasks for .NET 的文档？

A3：您可以在 [here](https://reference.aspose.com/tasks/net/) 找到 Aspose.Tasks for .NET 的文档。

### Q4：如何获取 Aspose.Tasks for .NET 的支持？

A4：有关 Aspose.Tasks for .NET 的支持，您可以访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

### Q5：是否提供用于测试的临时许可证？

A5：是的，您可以从 [here](https://purchase.aspose.com/temporary-license/) 获取用于测试的临时许可证。

## 常见问答

**Q：我可以将此方法用于现有的大型项目文件吗？**  
A：当然可以。树算法适用于任何 `Project` 实例，无论其大小如何。

**Q：该算法是否也会更新成本值？**  
A：示例侧重于工作量，但您可以通过以类似方式累计 `Tsk.Cost` 来扩展至成本。

**Q：支持哪些 .NET 版本？**  
A：Aspose.Tasks 支持 .NET Framework 4.5+、.NET Core 3.1+、.NET 5+ 和 .NET 6+。

**Q：如何处理每个任务的多个资源？**  
A：使用 `project.ResourceAssignments.Add(task, resource)` 添加每个资源；累计器会自动汇总它们的工作量。

---

**最后更新：** 2026-03-19  
**测试环境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
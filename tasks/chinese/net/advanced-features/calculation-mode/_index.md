---
date: 2026-03-24
description: 了解如何在 Aspose.Tasks for .NET 中设置计算模式，包括自动、手动计算模式以及无计算模式，以管理任务依赖关系。
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks for .NET 中设置计算模式
url: /zh/net/advanced-features/calculation-mode/
weight: 29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for .NET 中设置计算模式

## Introduction

Aspose.Tasks for .NET 是一个强大的 API，允许您以编程方式处理 Microsoft Project 文件。您将遇到的最重要设置之一是 **计算模式**，它控制任务日期和项目进度的更新方式。在本教程中，您将学习 **如何设置计算** 模式，探索 **自动计算模式**、**手动计算模式** 和 **无计算模式**，并了解这些选项如何影响 **管理任务依赖关系**、**创建项目开始日期** 和 **链接任务完成‑开始** 关系。

## Quick Answers
- **计算模式是什么？** 它决定任务日期是自动、手动还是根本不重新计算。  
- **为什么使用手动计算模式？** 以便完全控制何时刷新进度表，在批量更新时非常有用。  
- **默认模式是哪一个？** 自动计算模式，会在更改后立即更新日期。  
- **我可以在运行时更改模式吗？** 可以——只需在 `Project` 对象上设置 `CalculationMode` 属性。  
- **我需要许可证吗？** 生产环境使用需要有效的 Aspose.Tasks 许可证。

## What is “how to set calculation” in Aspose.Tasks?

在 Aspose.Tasks 中设置计算模式就像给 `Project.CalculationMode` 属性赋值一个枚举值一样简单。该枚举提供三种选项：`Automatic`、`Manual` 和 `None`。选择合适的模式取决于您的工作流——是需要即时更新、批处理还是完全控制。

## Prerequisites

在开始之前，请确保您拥有以下内容：

1. **Visual Studio** – 任意近期版本（2019、2022 或更高）。  
2. **Aspose.Tasks for .NET** – 从[此处](https://releases.aspose.com/tasks/net/)下载并安装库。  
3. **基本的 C# 知识** – 您应熟悉创建控制台应用程序以及使用 NuGet 包。

## Import Namespaces

在开始使用 Aspose.Tasks for .NET 之前，让我们导入必要的命名空间：

```csharp
using Aspose.Tasks;
using System;
```

## How to Set Calculation Mode

下面您将看到每种计算模式的逐步示例。代码块保持原样；我们对周围的说明进行了扩展以提高清晰度。

### Applying Automatic Calculation Mode

自动模式会在您修改任务或链接时立即重新计算日期。

#### Step 1: Create a new Project instance

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Step 2: Set project start date and add tasks

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Step 3: Link tasks (finish‑to‑start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Step 4: Verify recalculated dates

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Applying Manual Calculation Mode

手动模式会禁用自动更新，让您在强制重新计算之前批量处理更改。

#### Step 1: Create a new Project instance

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Step 2: Set project start date and add tasks

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Step 3: Verify task properties

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Step 4: Link tasks and verify dates (no automatic recalculation)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Applying None Calculation Mode

无计算模式会关闭所有内部计算。当您只需读取或导出数据且不进行任何进度更改时使用它。

#### Step 1: Create a new Project instance

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Step 2: Add a new task

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Step 3: Verify task properties (no automatic IDs)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Common Issues and Solutions

| 问题 | 产生原因 | 解决方案 |
|-------|----------------|-----|
| 链接任务后日期未更新 | 项目处于 **Manual** 或 **None** 模式 | 将 `project.CalculationMode = CalculationMode.Automatic`，或手动调用 `project.Calculate()` |
| 任务 ID 保持为 0 | 使用 **None** 模式会阻止 ID 生成 | 切换到 **Automatic** 或 **Manual** 模式，然后重新计算 |
| 使用 `ArgumentException` 链接失败 | 在 **Manual** 模式下未重新计算时，前置任务的开始日期晚于后置任务 | 确保开始日期正确，或在添加链接后重新计算 |

## Frequently Asked Questions

**Q1：我可以在运行时动态更改计算模式吗？**  
A1：可以，您可以在代码的任何位置修改 `CalculationMode` 属性，如需立即更新可调用 `project.Calculate()`。

**Q2：Aspose.Tasks 除了 Microsoft Project 之外，还支持其他项目管理文件格式吗？**  
A2：Aspose.Tasks 主要针对 Microsoft Project 格式，但也支持 Primavera P6 XML、Primavera DB 和 Asta Powerproject XML。

**Q3：Aspose.Tasks 适用于小型项目和企业级项目吗？**  
A3：完全适用。该 API 能够从简单的任务列表扩展到复杂的多阶段企业进度表。

**Q4：我可以将 Aspose.Tasks 与其他 .NET 库和框架集成吗？**  
A4：可以，您可以将 Aspose.Tasks 与 ASP.NET、WPF、Xamarin 或任何其他 .NET 技术结合，构建功能丰富的项目管理解决方案。

**Q5：是否有 Aspose.Tasks 用户的社区论坛或支持渠道？**  
A5：有，您可以访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获取社区支持和讨论。

---

**最后更新：** 2026-03-24  
**测试环境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
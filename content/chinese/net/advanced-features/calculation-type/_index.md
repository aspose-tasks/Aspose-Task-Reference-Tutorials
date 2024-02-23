---
title: Aspose.Tasks 中的计算类型
linktitle: Aspose.Tasks 中的计算类型
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 库中的计算类型在 .NET 项目中自定义值计算。
type: docs
weight: 30
url: /zh/net/advanced-features/calculation-type/
---
## 介绍

在本教程中，我们将探索 Aspose.Tasks for .NET 中的计算类型功能。 Aspose.Tasks 是一个功能强大的库，使 .NET 开发人员能够使用 Microsoft Project 文件，而无需在其系统上安装 Microsoft Project。计算类型允许我们定义如何计算项目中的任务和摘要任务的值。

## 先决条件

在我们开始之前，请确保您满足以下先决条件：

1. C# 和 .NET 框架的基础知识。
2. Visual Studio 安装在您的系统上。
3. 安装了 .NET 库的 Aspose.Tasks。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/net/).
4. 访问 Aspose.Tasks for .NET 文档以供参考，可用[这里](https://reference.aspose.com/tasks/net/).

## 导入命名空间

在深入研究示例之前，请确保导入必要的命名空间：

```csharp
using Aspose.Tasks;
using System;


```

## 第 1 步：创建一个新项目

首先，让我们创建一个新的项目对象：

```csharp
var project = new Project();
```

## 第 2 步：添加任务

现在，让我们向项目添加一个任务：

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## 步骤 3：定义扩展属性的计算类型

我们将创建一个扩展属性定义，并将计算类型设置为公式：

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## 步骤 4：定义汇总行的计算类型

接下来，我们将创建另一个扩展属性定义，其中使用 Average 汇总类型计算摘要任务的值：

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## 结论

在本教程中，我们探讨了如何在 Aspose.Tasks for .NET 中使用计算类型。通过定义扩展属性的计算类型，我们可以自定义项目内任务和摘要任务的值计算方式，提供更大的灵活性和控制力。

## 常见问题解答

### Q1：Aspose.Tasks 中的计算类型是什么？

A1：Aspose.Tasks 中的计算类型决定了如何计算项目内的任务和摘要任务的值，提供公式和汇总等选项。

### Q2：如何设置扩展属性的计算类型？

A2：您可以通过相应地定义扩展属性的 CalculationType 属性来设置扩展属性的计算类型。

### Q3：我可以为项目中的汇总行自定义计算类型吗？

A3：是的，Aspose.Tasks 允许您指定汇总行的计算类型，使您能够根据您的要求定制值计算。

### Q4：是否有不同的 Rollup Type 可用于摘要任务计算？

A4：是的，Aspose.Tasks 提供了 Average、Sum 和 Count 等各种 Rollup Type 来计算摘要任务的值。

### Q5：在哪里可以找到有关 Aspose.Tasks for .NET 的更多资源？

 A5：您可以浏览以下网站上提供的文档和社区支持论坛：[用于 .NET 的 Aspose.Tasks](https://reference.aspose.com/tasks/net/)以获得全面的指导和帮助。
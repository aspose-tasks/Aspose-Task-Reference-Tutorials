---
title: 在 Aspose.Tasks 中使用基线集合
linktitle: 在 Aspose.Tasks 中使用基线集合
second_title: Aspose.Tasks .NET API
description: 了解如何有效管理 Aspose.Tasks for .NET 中的基线。请按照我们的综合教程获取分步指导。
type: docs
weight: 20
url: /zh/net/advanced-features/working-with-baseline-collection/
---
## 介绍

Aspose.Tasks for .NET 是一个功能强大的库，使开发人员能够在其 .NET 应用程序中无缝地使用 Microsoft Project 文件。在其众多功能中，它为管理项目内的基线提供了强大的支持。基线对于项目管理至关重要，因为它们允许您将原始项目计划与当前状态进行比较，从而更好地跟踪和分析项目进度。

## 先决条件

在我们深入研究 Aspose.Tasks 中的基线集合之前，请确保您具备以下先决条件：

1. Visual Studio：在您的系统上安装 Visual Studio IDE。
2.  Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET 库：[下载链接](https://releases.aspose.com/tasks/net/).
3. 对 C# 的基本了解：熟悉 C# 编程语言。
4. Microsoft Project 文件：准备好 Microsoft Project 文件 (.mpp) 以用于测试目的。

## 导入命名空间

要开始在 Aspose.Tasks 中使用基线集合，您需要导入以下命名空间：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

现在，让我们将每个示例分解为多个步骤：

## 第 1 步：加载项目文件

首先，使用 Aspose.Tasks 加载 Microsoft Project 文件：

```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 第 2 步：获取资源

接下来，从项目中检索所需的资源：

```csharp
var resource = project.Resources.GetByUid(1);
```

## 步骤 3：显示基线信息

现在，显示有关与资源关联的基线的信息：

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## 第 4 步：迭代基线

迭代与资源关联的每个基线并打印相关信息：

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## 第 5 步：删除基线

删除与资源关联的所有基线：

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## 结论

在本教程中，我们探讨了如何在 Aspose.Tasks for .NET 中使用基线集合。通过遵循分步指南，您可以轻松管理 .NET 应用程序中的基线，从而实现有效的项目跟踪和分析。

## 常见问题解答

### Q1：Aspose.Tasks 可以处理大型项目文件吗？

A1：是的，Aspose.Tasks 经过优化，可有效处理大型项目文件，确保流畅的性能。

### Q2：Aspose.Tasks 是否与所有版本的 Microsoft Project 兼容？

A2：Aspose.Tasks支持Microsoft Project的各个版本，确保不同环境下的兼容性。

### Q3：我可以在 Aspose.Tasks 中自定义基线吗？

A3：是的，您可以根据您的项目要求使用 Aspose.Tasks for .NET 自定义基线。

### Q4：Aspose.Tasks 是否提供对云平台的支持？

A4：是的，Aspose.Tasks 支持与流行的云平台集成，提供部署灵活性。

### Q5：Aspose.Tasks 用户是否有社区论坛来寻求帮助和分享知识？

 A5: 是的，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)与社区互动并获得专家的帮助。
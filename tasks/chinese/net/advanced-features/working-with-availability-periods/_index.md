---
title: 在 Aspose.Tasks 中使用可用期
linktitle: 在 Aspose.Tasks 中使用可用期
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 高效管理资源可用期。本教程提供了有关在 .NET 项目中使用可用期的分步指南。
weight: 17
url: /zh/net/advanced-features/working-with-availability-periods/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中使用可用期

## 介绍

在本教程中，我们将探讨如何在 Aspose.Tasks for .NET 中使用可用期。可用期对于在项目管理场景中有效管理资源至关重要。我们将逐步指导您完成整个过程。

## 先决条件

在我们开始之前，请确保您满足以下先决条件：

1. Visual Studio：安装 Visual Studio 或任何其他用于 .NET 开发的首选 IDE。
2.  Aspose.Tasks for .NET：下载并安装 Aspose.Tasks for .NET 库[这里](https://releases.aspose.com/tasks/net/).
3. 对 C# 编程的基本了解：熟悉 C# 编程语言基础知识将会有所帮助。

## 导入命名空间

在深入代码之前，请确保导入必要的名称空间：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

让我们将示例代码分解为多个步骤：

## 第 1 步：创建一个新的项目实例

```csharp
var project = new Project();
```

此行初始化 Project 类的新实例，它代表 Aspose.Tasks 中的一个项目。

## 第 2 步：添加资源

```csharp
var resource = project.Resources.Add("Work Resource");
```

在这里，我们向项目添加一个名为“Work Resource”的新资源。

## 第 3 步：定义可用期限

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

我们称之为`GetPeriods()`检索可用时段集合的方法。

## 步骤 4：向资源添加可用期

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

我们迭代上一步中获得的可用期集合并将它们添加到资源中。

## 第 5 步：显示可用期详细信息

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

最后，我们循环遍历与资源关联的可用期并打印其详细信息，包括开始日期、结束日期和可用单位。

## 结论

在本教程中，我们学习了如何在 Aspose.Tasks for .NET 中使用可用期。通过遵循分步指南，您可以有效地管理项目管理应用程序中的资源可用性。

## 常见问题解答

### Q1：我可以在商业项目中使用 Aspose.Tasks for .NET 吗？

 A1：是的，Aspose.Tasks for .NET可以用于商业项目。您可以购买许可证[这里](https://purchase.aspose.com/buy).

### 问题 2：Aspose.Tasks for .NET 是否有免费试用版？

A2：是的，您可以获得 Aspose.Tasks for .NET 的免费试用版[这里](https://releases.aspose.com/).

### Q3：在哪里可以找到 Aspose.Tasks for .NET 的文档？

A3：你可以找到文档[这里](https://reference.aspose.com/tasks/net/).

### Q4：如何获得 Aspose.Tasks for .NET 支持？

A4：您可以从社区论坛获得支持[这里](https://forum.aspose.com/c/tasks/15).

### Q5：你们提供 Aspose.Tasks for .NET 的临时许可证吗？

 A5：是的，可以使用临时许可证[这里](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

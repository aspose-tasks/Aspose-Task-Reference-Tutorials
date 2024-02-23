---
title: Aspose.Tasks 中可用时段的集合
linktitle: Aspose.Tasks 中可用时段的集合
second_title: Aspose.Tasks .NET API
description: 了解如何管理 Aspose.Tasks for .NET 中资源的可用期。本分步教程将指导您添加、更新和删除可用期，确保有效的项目资源规划。
type: docs
weight: 18
url: /zh/net/advanced-features/availability-period-collection/
---
## 介绍

在本教程中，我们将探讨如何在 Aspose.Tasks for .NET 中使用资源的可用期集合。管理可用期对于项目管理至关重要，它使我们能够定义资源何时可用于项目内的任务。

## 先决条件

在我们开始之前，请确保您具备以下条件：

1. Visual Studio：确保您的系统上安装了 Visual Studio。
2.  Aspose.Tasks for .NET：下载并安装 Aspose.Tasks for .NET 库[这里](https://releases.aspose.com/tasks/net/).
3. 基本了解：熟悉 C# 和 .NET 框架。

## 导入命名空间

首先，我们需要将必要的命名空间导入到我们的项目中：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

让我们将示例代码分解为多个步骤并理解每个部分：

## 第 1 步：初始化项目和资源

```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

在这里，我们加载一个项目文件并通过其 ID 获取特定资源。

## 第 2 步：清除现有的可用期限

```csharp
resource.AvailabilityPeriods.Clear();
```

我们清除与资源相关的所有现有可用期。

## 第 3 步：添加可用时段

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

我们迭代可用性周期的集合并将它们添加到资源中。

## 第 4 步：插入新的可用期

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

我们为 2013 年创建一个新的可用期并将其插入到集合中。

## 第 5 步：显示可用期限

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

我们打印出与资源相关的每个可用期的计数和详细信息。

## 步骤 6：将可用期复制到另一个资源

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

我们将可用性周期从一种资源复制到另一种资源。

## 第 7 步：更新和删除可用期

```csharp
//更新特定期间的可用单位
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

//删除特定时期
otherResource.AvailabilityPeriods.Remove(period2013);
```

我们更新某个时期的可用单位并从集合中删除特定时期。

## 结论

在本教程中，我们学习了如何在 Aspose.Tasks for .NET 中使用可用期集合。管理资源可用性对于有效的项目规划和执行至关重要。

## 常见问题解答

### Q1：我可以在可用期限中添加自定义字段吗？

A1：不，Aspose.Tasks for .NET 中的可用期不支持自定义字段。

### Q2：可用期限与特定任务相关吗？

A2：不，可用期与资源相关联，并定义资源何时可用于一般任务。

### Q3：我可以从外部来源导入可用时段吗？

A3：是的，您可以使用 Aspose.Tasks for .NET API 从各种数据源导入可用时段。

### Q4：如何处理重叠的可用期？

A4：Aspose.Tasks for .NET 不提供内置机制来处理重叠周期。您可能需要实现自定义逻辑来管理此类场景。

### Q5：资源的可用期限有限制吗？

A5：资源可以拥有的可用周期数没有预定义限制，但周期数过多可能会导致性能下降。
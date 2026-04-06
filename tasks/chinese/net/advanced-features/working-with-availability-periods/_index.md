---
date: 2026-04-06
description: 了解如何使用 Aspose.Tasks for .NET 将资源添加到项目并设置资源可用期间。一步步指南，帮助管理资源日历。
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: 在 Aspose.Tasks 中使用可用期间
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 中向项目添加资源并设置可用性
url: /zh/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将资源添加到项目并在 Aspose.Tasks 中设置可用性

## 介绍

在本教程中，您将学习**如何将资源添加到项目**，随后使用 Aspose.Tasks .NET 库定义其可用时间段。管理资源日历对于实现真实的项目进度至关重要，以下步骤将带您完成整个过程——从创建项目实例到打印每个时间段的详细信息。

## 快速答案
- **主要目标是什么？** 将资源添加到项目并配置其可用时间段。  
- **需要哪个库？** Aspose.Tasks for .NET。  
- **生产环境需要许可证吗？** 是的，需要商业许可证。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **实现时间？** 基本场景通常在 15 分钟以内完成。

## 什么是“将资源添加到项目”？

将资源添加到项目会为人员、设备或材料创建一个占位符，以便可以分配给任务。资源创建后，您可以**设置资源可用性**，定义其工作日历，让调度器遵循这些约束。

## 为什么要配置工作计划和可用时间段？

- **准确的计划：** 仅在资源实际空闲时安排任务。  
- **成本控制：** 可用单位反映兼职工作量，帮助您正确计算人工成本。  
- **资源平衡：** 引擎在了解每个资源的日历后，可自动平衡超额分配。

## 前置条件

1. Visual Studio（或任何兼容 .NET 的 IDE）。  
2. Aspose.Tasks for .NET – 从 [here](https://releases.aspose.com/tasks/net/) 下载。  
3. 基础 C# 知识。

## 导入命名空间

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 如何将资源添加到项目？

### 步骤 1：创建新的 `Project` 实例

```csharp
var project = new Project();
```

此对象表示内存中的整个项目文件。

### 步骤 2：向项目添加资源

```csharp
var resource = project.Resources.Add("Work Resource");
```

此调用会创建一个名为 *Work Resource* 的**资源**，您随后可以将其分配给任务。

### 步骤 3：定义可用时间段

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` 是一个辅助方法（实现未显示），返回 `AvailabilityPeriod` 对象的集合。每个时间段指定开始日期、结束日期以及资源可用的单位（全职工作量的百分比）。

### 步骤 4：将时间段添加到资源

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

这里我们通过遍历集合并将每个时间段添加到资源的日历中，**设置资源可用性**。

### 步骤 5：显示可用性详情

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

控制台输出可帮助您验证时间段是否已正确存储。

## 常见陷阱与提示

- **日期精度：** `AvailableFrom` 和 `AvailableTo` 为 `DateTime` 值；如果需要整天的时间段，请确保将其设置为午夜。  
- **单位范围：** 有效值为 0‑100 %；超出此范围会抛出异常。  
- **重叠时间段：** 重叠的时间段会自动合并，但保持它们独立更易于阅读。

## 常见问题

### Q1：我可以在商业项目中使用 Aspose.Tasks for .NET 吗？
A1：可以，Aspose.Tasks for .NET 可用于商业项目。您可以在 [here](https://purchase.aspose.com/buy) 购买许可证。

### Q2：Aspose.Tasks for .NET 是否提供免费试用？
A2：是的，您可以在 [here](https://releases.aspose.com/) 获取 Aspose.Tasks for .NET 的免费试用版。

### Q3：在哪里可以找到 Aspose.Tasks for .NET 的文档？
A3：文档位于 [here](https://reference.aspose.com/tasks/net/)。

### Q4：如何获取 Aspose.Tasks for .NET 的支持？
A4：您可以在社区论坛 [here](https://forum.aspose.com/c/tasks/15) 获取支持。

### Q5：是否提供 Aspose.Tasks for .NET 的临时许可证？
A5：是的，临时许可证可在 [here](https://purchase.aspose.com/temporary-license/) 获取。

---

**最后更新：** 2026-04-06  
**测试环境：** Aspose.Tasks for .NET（最新稳定版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
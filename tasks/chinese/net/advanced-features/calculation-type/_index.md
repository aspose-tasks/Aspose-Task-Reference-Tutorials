---
date: 2026-03-24
description: 学习如何在 Aspose.Tasks for .NET 中设置计算，示例包括计算汇总值、定义计算公式以及配置汇总统计。
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中设置计算类型
url: /zh/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中设置计算类型

## 介绍

如果您需要 **如何设置计算** 规则来处理 Microsoft Project 文件中的任务和汇总行，本教程将使用 Aspose.Tasks for .NET 为您详细演示。我们将完整演示一个 **计算类型示例**，展示如何 **计算汇总值**，并说明如何 **定义计算公式** 和 **配置回滚汇总** 以用于扩展属性。完成后，您将能够向项目添加任务，设置自定义计算逻辑，并自信地控制回滚行为。

## 快速答案
- **主要目的是什么？** 在 Project 文件中控制任务和汇总值的计算方式。  
- **使用哪个 API 类？** `ExtendedAttributeDefinition` 与 `CalculationType` 和 `SummaryRowsCalculationType` 一起使用。  
- **我可以使用公式吗？** 可以 – 将 `CalculationType = CalculationType.Formula` 并提供公式字符串。  
- **如何回滚汇总值？** 使用 `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` 并指定如 `Average` 的 `RollupType`。  
- **我需要许可证吗？** 生产环境需要有效的 Aspose.Tasks 许可证。

## 什么是计算类型以及如何设置计算？

`CalculationType` 告诉 Aspose.Tasks 如何计算扩展属性的值。您可以选择静态值、公式，或让库从子任务回滚值。正确设置计算对于希望项目能够在不手动更新的情况下反映自定义业务规则至关重要。

## 为什么使用计算类型来计算汇总值？

当项目包含汇总任务时，您通常需要汇总行显示聚合数据（例如，总成本、平均工期）。通过配置 `SummaryRowsCalculationType` 和 `RollupType` 来 **计算汇总值**，Aspose.Tasks 可以在您修改各个任务时自动保持这些聚合数据同步。

## 前提条件

在开始之前，请确保您具备：

1. 对 C# 和 .NET 框架的基本了解。  
2. 在机器上安装了 Visual Studio（任意较新版本）。  
3. 已安装 Aspose.Tasks for .NET 库 – 可从 [here](https://releases.aspose.com/tasks/net/) 下载。  
4. 可访问官方 Aspose.Tasks for .NET 文档供参考，链接在 [here](https://reference.aspose.com/tasks/net/)。

## 导入命名空间

在深入示例之前，请确保导入必要的命名空间：

```csharp
using Aspose.Tasks;
using System;
```

## 步骤 1：创建新项目

首先，我们创建一个空的 `Project` 对象，用于保存任务和自定义属性。

```csharp
var project = new Project();
```

## 步骤 2：向项目添加任务

现在我们 **添加任务项目** 数据，通过创建一个简单任务，设置其开始日期，并给它一天的持续时间。

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## 步骤 3：为扩展属性定义计算类型（公式示例）

这里我们创建一个扩展属性定义，其值通过公式计算。这演示了一个 **计算类型示例**，并展示了如何 **定义计算公式**。

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## 步骤 4：为汇总行定义计算类型（配置回滚汇总）

接下来，我们创建另一个扩展属性定义，指示 Aspose.Tasks 使用 *Average* 回滚类型来 **配置回滚汇总**。这是 **计算汇总值**（如成本、工时或自定义字段）的典型方式。

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## 常见问题与故障排除

| 症状 | 可能原因 | 解决办法 |
|------|----------|----------|
| 公式返回 `null` | 公式中的字段引用不正确 | 验证括号内的字段名称（例如 `[Start]` 而不是 `[stARt]`）。 |
| 汇总行显示 0 | `SummaryRowsCalculationType` 未设置或 `RollupType` 错误 | 确保 `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` 并选择合适的 `RollupType`。 |
| 添加属性后项目加载失败 | 属性定义与任务使用不匹配 | 在将属性分配给任何任务之前 **先** 添加属性定义。 |

## 结论

在本教程中，我们介绍了在 Aspose.Tasks for .NET 中 **如何设置计算** 规则，从创建简单任务到定义基于公式和基于回滚的计算类型。掌握这些设置后，您即可细粒度地 **计算汇总值**，实现更丰富的项目分析，而无需手动使用电子表格。

## 常见问答

### Q1：Aspose.Tasks 中的计算类型是什么？

A1：Aspose.Tasks 中的计算类型决定了项目中任务和汇总任务的值如何计算，提供了公式（Formula）和回滚（Rollup）等选项。

### Q2：如何为扩展属性设置计算类型？

A2：可以通过相应地设置其 CalculationType 属性来为扩展属性设置计算类型。

### Q3：我可以自定义项目中汇总行的计算类型吗？

A3：是的，Aspose.Tasks 允许您为汇总行指定计算类型，从而根据需求定制值的计算方式。

### Q4：汇总任务计算是否有不同的回滚类型可用？

A4：是的，Aspose.Tasks 提供了多种回滚类型，例如 Average、Sum 和 Count，用于计算汇总任务的值。

### Q5：在哪里可以找到更多关于 Aspose.Tasks for .NET 的资源？

A5：您可以在 [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) 上的文档和社区支持论坛中查找全面的指南和帮助。

---

**最后更新：** 2026-03-24  
**测试环境：** Aspose.Tasks for .NET（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Aspose.Tasks 中的成本应计类型
linktitle: Aspose.Tasks 中的成本应计类型
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效管理项目成本。定义成本应计类型以准确跟踪预算。
weight: 19
url: /zh/net/calendar-scheduling/cost-accrual-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的成本应计类型

## 介绍

在项目管理中，准确跟踪成本对于维持预算控制和确保项目成功至关重要。 Aspose.Tasks for .NET 提供了一套强大的工具来管理项目成本，包括定义不同成本应计类型的能力。本教程将引导您完成使用 Aspose.Tasks for .NET 理解和实现成本应计类型的过程。

## 先决条件

在我们开始之前，请确保您满足以下先决条件：

### 1.安装Aspose.Tasks for .NET

首先，您需要在开发环境中安装 Aspose.Tasks for .NET。您可以从以下位置下载该库[下载页面](https://releases.aspose.com/tasks/net/)并按照提供的安装说明进行操作。

### 2. 熟悉.NET Framework

遵循本教程中的示例需要具备 .NET 框架和 C# 编程语言的基本知识。

## 导入命名空间

首先，我们导入必要的命名空间来访问 .NET 项目中的 Aspose.Tasks 功能：

```csharp

```

现在我们已经介绍了先决条件并导入了所需的命名空间，让我们继续将每个示例分解为多个步骤。

## 第 1 步：加载项目文件

```csharp
var project = new Project("Project2.mpp");
```

首先，我们需要将项目文件加载到我们的应用程序中。我们创建一个新的`Project`对象并使用我们的项目文件的路径对其进行初始化。

## 第 2 步：访问资源

```csharp
var resource = project.Resources.GetById(1);
```

接下来，我们访问要应用成本应计类型的资源。我们使用`GetById`的方法`Resources`集合并将资源 ID 作为参数传递。

## 步骤 3：设置成本应计类型

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

在这里，我们设置资源的成本应计类型。在本例中，我们将其设置为`CostAccrualType.End`，这意味着在剩余工作量为零之前不会产生成本。

## 第 4 步：处理项目

设置成本应计类型后，您可以根据需要继续处理项目，执行其他操作或计算。

## 结论

了解和实施成本应计类型对于有效的项目成本管理至关重要。借助 Aspose.Tasks for .NET，您可以根据项目需求轻松定义和自定义成本应计类型，确保整个项目生命周期中准确的成本跟踪和预算控制。

## 常见问题解答

### Q1：我可以同时更改多个资源的成本应计类型吗？

A1：是的，您可以循环遍历资源集合并单独为每个资源设置成本应计类型。

### Q2：除了“结束”之外，还有哪些可用的成本应计类型？

A2：Aspose.Tasks for .NET 提供了几种其他成本应计类型，例如`Start`, `Prorated`， 和`Duration`.

### 问题 3：如何确定资源当前的成本应计类型？

 A3：您可以使用以下命令检索当前的成本应计类型：`Get`资源对象上的方法。

### 问题 4：我可以对同一项目中的不同任务应用不同的成本应计类型吗？

A4：是的，您可以为项目中的每个任务和资源单独设置成本应计类型。

### Q5：Aspose.Tasks for .NET 支持自定义成本应计类型吗？

A5：从最新版本开始，Aspose.Tasks for .NET 不支持定义自定义成本应计类型。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Aspose.Tasks 中的计算模式
linktitle: Aspose.Tasks 中的计算模式
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中有效管理计算模式，以简化项目调度和任务依赖性。
weight: 29
url: /zh/net/advanced-features/calculation-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的计算模式

## 介绍

Aspose.Tasks for .NET 是一个功能强大的 API，允许开发人员在其 .NET 应用程序中以编程方式使用 Microsoft Project 文件。使用项目文件的一个重要方面是管理计算模式，这决定了任务和项目进度表的计算和更新方式。在本教程中，我们将深入研究 Aspose.Tasks for .NET 支持的各种计算模式，并演示如何有效地使用它们。

## 先决条件

在开始之前，请确保您具备以下条件：

1. Visual Studio：确保您的系统上安装了 Visual Studio。
2.  Aspose.Tasks for .NET：下载并安装 Aspose.Tasks for .NET 库[这里](https://releases.aspose.com/tasks/net/).
3. 对 C# 编程的基本了解：熟悉 C# 编程概念。

## 导入命名空间

在开始使用 Aspose.Tasks for .NET 之前，让我们导入必要的命名空间：

```csharp
using Aspose.Tasks;
using System;


```

## 应用自动计算模式

### 第 1 步：创建一个新的项目实例

初始化一个新的`Project`对象并设置其`CalculationMode`财产给`CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### 第 2 步：设置项目开始日期并添加任务

定义项目的开始日期并向其添加任务。

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 第 3 步：链接任务

建立任务之间的依赖关系。

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### 第 4 步：验证重新计算的日期

检查日期是否已自动重新计算。

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
//根据需要添加更多验证
```

## 应用手动计算模式

### 第 1 步：创建一个新的项目实例

初始化一个新的`Project`对象并设置其`CalculationMode`财产给`CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### 第 2 步：设置项目开始日期并添加任务

定义项目的开始日期并向其添加任务。

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### 步骤 3：验证任务属性

检查手动模式下任务属性设置是否正确。

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
//根据需要添加更多验证
```

### 第 4 步：链接任务并验证日期

将任务链接在一起并检查它们的日期是否未重新计算。

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## 应用无计算模式

### 第 1 步：创建一个新的项目实例

初始化一个新的`Project`对象并设置其`CalculationMode`财产给`CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### 第 2 步：添加新任务

向项目添加新任务。

```csharp
var task = project.RootTask.Children.Add("Task");
```

### 步骤 3：验证任务属性

检查任务属性是否未自动计算。

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
//根据需要添加更多验证
```

## 结论

在本教程中，我们探索了 Aspose.Tasks for .NET 中可用的计算模式，并学习了如何在实际场景中应用它们。无论您需要自动、手动还是无计算模式，Aspose.Tasks 都能提供满足您项目需求的灵活性。

## 常见问题解答

### Q1：我可以在运行时动态改变计算模式吗？

A1：是的，您可以在运行时的任何时刻通过修改`CalculationMode`财产。

### Q2：Aspose.Tasks 是否支持除 Microsoft Project 之外的其他项目管理文件格式？

A2：Aspose.Tasks 主要关注 Microsoft Project 文件格式，但它也支持其他格式，如 Primavera P6 XML、Primavera DB 和 Asta Powerproject XML。

### Q3：Aspose.Tasks 适合小型和企业级项目吗？

A3：当然！ Aspose.Tasks 旨在以其全面的功能和强大的 API 来满足小型和企业级项目的需求。

### Q4：我可以将 Aspose.Tasks 与其他 .NET 库和框架集成吗？

A4：是的，您可以将 Aspose.Tasks 与其他 .NET 库和框架无缝集成，以增强应用程序的功能。

### Q5：Aspose.Tasks 用户有可用的社区论坛或支持渠道吗？

 A5: 是的，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区支持和讨论。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

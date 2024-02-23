---
title: 在 Aspose.Tasks 中处理 MS Project 拆分部分
linktitle: 处理 Aspose.Tasks 中的拆分部分
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 高效处理 MS Project 拆分部分。增强您的项目管理工作流程。
type: docs
weight: 18
url: /zh/net/rate-recurring-tasks/split-parts/
---

## 介绍
使用 Aspose.Tasks for .NET 时，管理 MS Project 拆分部分可能是项目管理的一个重要方面。在本教程中，我们将探索如何使用分步指导有效处理拆分零件。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. 安装 Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET[网站](https://releases.aspose.com/tasks/net/).
   
2. 对 C# 的基本了解：熟悉 C# 编程语言将会很有帮助。

## 导入命名空间
在您的 C# 代码中，确保导入必要的命名空间：
```csharp
    using Aspose.Tasks;
    using System;
    
```

## 第1步：创建项目实例
```csharp
var project = new Project();
```
创建一个新实例`Project`班级。
## 第 2 步：设置项目开始和完成日期
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
设置项目的开始和完成日期。
## 第 3 步：添加任务
```csharp
var task = project.RootTask.Children.Add("Task1");
```
向项目添加新任务。
## 步骤 4：设置任务属性
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
设置任务的手动状态、开始日期和持续时间等属性。
## 步骤 5：添加资源分配
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
将资源分配添加到任务中。
## 第 6 步：设置分配属性
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
设置作业的开始日期、工作和完成日期等属性。
## 第 7 步：生成时间分段数据
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
根据项目日历生成任务的时间分段数据。
## 第 8 步：拆分任务
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
在规定的时间内将任务分成多个部分。
## 第 9 步：迭代分割部分
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
迭代任务的各个部分并打印它们的开始和完成日期。

## 结论
在 Aspose.Tasks for .NET 中有效处理 MS Project 拆分部分对于项目管理效率至关重要。通过遵循本教程中概述的步骤，您可以无缝管理拆分任务并增强项目管理工作流程。
## 常见问题解答
### 问：我可以将 Aspose.Tasks for .NET 与其他 .NET 框架一起使用吗？
答：是的，Aspose.Tasks for .NET 与各种 .NET 框架兼容，包括 .NET Core 和 .NET Standard。
### 问：Aspose.Tasks for .NET 是否有免费试用版？
答：是的，您可以从以下位置获得免费试用[这里](https://releases.aspose.com/).
### 问：Aspose.Tasks for .NET 支持资源管理吗？
答：是的，Aspose.Tasks for .NET 允许您有效地管理项目资源。
### 问：我可以使用 Aspose.Tasks for .NET 自定义项目日历吗？
答：当然，您可以根据您的项目需求定制项目日历。
### 问：在哪里可以找到对 Aspose.Tasks for .NET 的支持？
答：您可以在以下网站上找到支持和帮助：[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).
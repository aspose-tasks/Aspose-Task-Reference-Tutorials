---
title: 使用 Aspose.Tasks 自定义甘特图列
linktitle: Aspose.Tasks 中的甘特图列
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中定制甘特图列以有效地显示特定任务信息。
type: docs
weight: 21
url: /zh/net/tasks-project-management/gantt-chart-columns/
---
## 介绍
甘特图是项目管理中的基本工具，提供任务、时间表和资源的可视化表示。 Aspose.Tasks for .NET 提供了操作甘特图的强大功能，包括自定义列以显示特定任务信息。在本教程中，我们将探索如何使用 Aspose.Tasks for .NET 处理甘特图列。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1. 安装：Aspose.Tasks for .NET 安装在您的系统上。如果没有，请从以下位置下载并安装[这里](https://releases.aspose.com/tasks/net/).
2. .NET 开发环境：C# 和 .NET 框架的应用知识。
3. 示例项目文件：有一个示例 Microsoft Project 文件（`.mpp`）方便进行实验。如果没有，可以在 MS Project 中创建一个简单的项目并保存。

## 导入命名空间
首先，您需要导入必要的命名空间以使用 Aspose.Tasks for .NET：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 第 1 步：加载项目文件
使用加载项目文件`Project`Aspose.Tasks 提供的类：
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## 步骤 2：定义甘特图列
定义要在甘特图中显示的列。您可以指定内置字段或创建自定义字段：
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## 第 3 步：迭代列
迭代定义的列以访问其属性并显示信息：
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## 第 4 步：将甘特图保存为 CSV
将具有已定义列的甘特图保存到 CSV 文件：
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
通过执行这些步骤，您可以有效地使用 Aspose.Tasks for .NET 中的甘特图列，从而允许您根据需要自定义和显示任务信息。

## 结论
掌握 Aspose.Tasks for .NET 中甘特图列的操作为根据您的特定需求定制项目管理视觉效果提供了无限的可能性。通过遵循本教程中概述的步骤，您可以有效地处理任务信息并增强项目的清晰度和组织性。
## 常见问题解答
### 问：我可以在 Aspose.Tasks for .NET 中创建自定义列吗？
答：是的，您可以根据您的项目需求定义自定义列来显示特定的任务属性。
### 问：Aspose.Tasks for .NET 是否与所有版本的 Microsoft Project 文件兼容？
答：Aspose.Tasks for .NET 支持各种版本的 Microsoft Project 文件，确保不同项目环境之间的兼容性。
### 问：如何使用 Aspose.Tasks for .NET 处理复杂的项目结构？
答：Aspose.Tasks for .NET 提供全面的 API 和功能来管理复杂的项目结构，提供灵活性和可扩展性。
### 问：我可以添加到甘特图中的列数有限制吗？
答：Aspose.Tasks for .NET 提供了广泛的自定义选项，允许您无限制地向甘特图添加大量列。
### 问：在哪里可以找到 Aspose.Tasks for .NET 的其他支持和资源？
答：您可以浏览 Aspose.Tasks for .NET 提供的文档、社区论坛和支持渠道，以获得全面的资源和帮助。
---
title: Aspose.Tasks 中轻松的 MS 项目重复间隔
linktitle: 管理 Aspose.Tasks 中的重复间隔
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 轻松管理 MS Project 中的重复间隔。
type: docs
weight: 12
url: /zh/net/rate-recurring-tasks/recurring-intervals/
---
## 介绍
您是否希望使用 Aspose.Tasks for .NET 在 Microsoft Project 文件中有效管理重复间隔？这个全面的教程将逐步指导您完成整个过程，确保您可以轻松处理项目中的重复间隔。在深入学习本教程之前，我们先了解一些先决条件，以确保您已准备好开始使用。
## 先决条件
在继续本教程之前，请确保您具备以下条件：
1. C# 编程知识：需要对 C# 编程语言及其语法有基本的了解。
2. 安装了 Visual Studio：确保您的系统上安装了 Visual Studio，用于编码和编译 .NET 应用程序。
3. Aspose.Tasks for .NET 库：下载并安装 Aspose.Tasks for .NET 库。你可以从[这里](https://releases.aspose.com/tasks/net/).

## 导入命名空间
首先导入必要的命名空间以访问 Aspose.Tasks for .NET 库提供的功能。
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
现在，让我们将每个示例分解为多个步骤并详细解释它们。
## 第 1 步：初始化项目对象：
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
在这里，我们初始化一个新的实例`Project`类，通过提供 Microsoft Project 文件的路径。
## 第 2 步：设置状态日期：
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
此步骤将项目的状态日期设置为其开始日期。
## 第 3 步：访问甘特图视图：
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
我们访问项目的甘特图视图。
## 第 4 步：阅读进度线：
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
此步骤从甘特图视图中检索进度线的重复间隔。
## 步骤 5：显示间隔信息：
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
在这里，我们显示有关间隔、每周周数和每周天数的信息。
## 第 6 步：重新定义重复间隔：
```csharp
var newInterval = new RecurringInterval();
```
我们创建一个新实例`RecurringInterval`重新定义重复间隔。
## 第 7 步：设置每月进度线：
```csharp
//按天设置每月进度线。
interval.MonthlyDay = true;
//设置每月进度线的天数。
interval.MonthlyDayDayNumber = 1;
//设置每月进度线的月份数。
interval.MonthlyDayMonthNumber = 1;
//按预定义的第一天或最后一天设置进度线。
interval.MonthlyFirstLast = true;
//设置每月进度线的第一天或最后一天类型。
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
//设置进度线的月份数。
interval.MonthlyFirstLastMonthNumber = 1;
```
这些步骤根据指定的参数配置每月进度线。
## 第 8 步：更新进度线：
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
我们使用新定义的重复间隔更新甘特图视图中的进度线。
## 第 9 步：将项目另存为 PDF：
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
最后，我们将更新后的重复间隔的项目保存为 PDF 文件。

## 结论
总之，通过该库提供的全面功能，使用 Aspose.Tasks for .NET 管理 Microsoft Project 文件中的重复间隔变得非常简单。通过遵循本教程中概述的分步指南，您可以有效地处理项目中的重复间隔，从而提高工作效率和组织性。
### 常见问题解答
### 我可以将 Aspose.Tasks for .NET 与其他编程语言一起使用吗？
是的，Aspose.Tasks for .NET 可以与任何 .NET 支持的语言一起使用，例如 C# 和 VB.NET。
### Aspose.Tasks for .NET 是否有试用版？
是的，您可以从以下位置下载免费试用版[这里](https://releases.aspose.com/).
### 如何获得 Aspose.Tasks for .NET 支持？
您可以从 Aspose.Tasks 论坛获得支持[这里](https://forum.aspose.com/c/tasks/15).
### 我可以购买 Aspose.Tasks for .NET 的临时许可证吗？
是的，您可以从以下位置购买临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以找到 Aspose.Tasks for .NET 的完整文档？
完整的文档可以找到[这里](https://reference.aspose.com/tasks/net/).
---
title: 使用 Aspose.Tasks 处理 MS 项目进度线
linktitle: 处理 Aspose.Tasks 中的进度线
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 操作 MS Project 文件中的进度线，从而增强项目可视化和管理。
type: docs
weight: 15
url: /zh/net/project-management-integration/progress-lines/
---
## 介绍
Microsoft Project (MS Project) 是一个强大的项目管理工具，允许用户跟踪项目的各个方面。 MS Project 的一项重要功能是能够可视化进度线，这有助于利益相关者了解项目的状态和轨迹。在本教程中，我们将探索如何使用 .NET 的 Aspose.Tasks 库处理 MS Project 中的进度线。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1. Visual Studio：安装 Visual Studio 或任何其他首选的 .NET 开发环境。
2.  Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET[这里](https://releases.aspose.com/tasks/net/).
3. C# 基础知识：熟悉 C# 编程语言将会很有帮助。

## 导入命名空间
首先，让我们导入必要的命名空间：
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
现在，让我们分解处理进度线的每个步骤：
## 第 1 步：加载项目文件
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
在这里，我们加载 MS Project 文件`Project2.mpp`并设置其状态日期。
## 第 2 步：定义甘特图视图
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
我们将项目的视图转换为甘特图视图以进行进一步的操作。
## 第 3 步：定义进度线
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
我们初始化甘特图视图的进度线。
## 步骤 4：配置进度线设置
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
在这里，我们为进度线设置各种属性，例如线条颜色、图案、字体等。
## 第 5 步：检查进度线配置
```csharp
//输出进度线设置
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
//输出其他设置...
```
我们输出配置的进度线设置以进行验证。
## 第 6 步：保存项目文件
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
最后，我们保存修改后的带有进度线的项目文件。

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 处理 MS Project 进度线。通过执行这些步骤，您可以以编程方式有效地自定义和可视化 MS Project 文件中的进度线。
## 常见问题解答
### 问：我可以进一步自定义进度线的外观吗？
答：是的，您可以调整各种属性，例如线条颜色、图案和字体来满足您的要求。
### 问：Aspose.Tasks 是否支持其他项目管理功能？
答：是的，Aspose.Tasks 为操作 MS Project 文件的各个方面提供了广泛的支持，包括任务、资源和日历。
### 问：我可以将 Aspose.Tasks 与其他 .NET 库集成吗？
答：当然，Aspose.Tasks 旨在与其他 .NET 库无缝集成，让您进一步增强项目管理应用程序。
### 问：是否有 Aspose.Tasks 支持的社区论坛？
答：是的，您可以在 Aspose.Tasks 论坛上找到有用的资源并寻求帮助。[这里](https://forum.aspose.com/c/tasks/15).
### 问：Aspose.Tasks 是否提供用于评估目的的临时许可证？
答：是的，您可以从以下位置获取临时评估许可证：[这里](https://purchase.aspose.com/temporary-license/).
---
title: 掌握 Aspose.Tasks 中的甘特图视图
linktitle: Aspose.Tasks 中的甘特图视图
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 Microsoft Project 文件中自定义甘特图视图。高效项目管理的分步指南。
type: docs
weight: 22
url: /zh/net/tasks-project-management/gantt-chart-views/
---
## 介绍
甘特图是项目管理中用于可视化任务、时间表和依赖关系的强大工具。 Aspose.Tasks for .NET 提供了在 Microsoft Project 文件中处理甘特图视图的强大功能。在本教程中，我们将探索如何利用 Aspose.Tasks 操作甘特图视图、自定义其外观并将其另存为 PDF 文件。
## 先决条件
在继续之前，请确保您具备以下先决条件：
### 1.安装Aspose.Tasks for .NET
确保您已安装 Aspose.Tasks for .NET。您可以从以下位置下载该库[这里](https://releases.aspose.com/tasks/net/)并按照文档中提供的安装说明进行操作[这里](https://reference.aspose.com/tasks/net/).
### 2. 微软项目文件
准备 Microsoft Project 文件（`Project2.mpp`）您将使用它来处理甘特图视图。
### 3. C#和.NET Framework基础知识
本教程假设您对 C# 编程语言和 .NET 框架有基本的了解。
## 导入命名空间
在开始在 Aspose.Tasks 中使用甘特图视图之前，您需要将必要的命名空间导入到 C# 代码中。您可以这样做：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

让我们将提供的示例代码分解为多个步骤并详细解释每个步骤：
## 第 1 步：加载项目文件
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
此步骤涉及加载 Microsoft Project 文件（`Project2.mpp` ）到一个实例`Project`班级。
## 第 2 步：设置状态日期
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
在这里，我们将项目的状态日期设置为其开始日期。
## 第 3 步：访问甘特图视图
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
我们从项目中访问甘特图视图。 Aspose.Tasks 允许访问甘特图、网络图和任务使用情况等视图。
## 第 4 步：自定义甘特图视图
现在，让我们自定义甘特图视图的各个方面：
### 设置栏舍入
```csharp
view.BarRounding = false;
```
这设置甘特图上的条是否四舍五入到最近的一天。
### 设置条形尺寸
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
这决定了图表中甘特条的高度。
### 隐藏滚动条
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
指定展开摘要任务时是否隐藏滚动条。
### 设置非工作时间颜色
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
定义甘特图上非工作时间的颜色。
### 卷起甘特条
```csharp
view.RollUpGanttBars = true;
```
指定甘特图上的条是否必须卷起。
### 显示条形分割
```csharp
view.ShowBarSplits = true;
```
确定是否必须在甘特图上显示任务拆分。
### 展示图纸
```csharp
view.ShowDrawings = true;
```
指定是否必须显示甘特图上的绘图。
### 时间刻度大小百分比
```csharp
view.TimescaleSizePercentage = 10;
```
设置百分比以调整时间刻度层上单位之间的间距。
## 第 5 步：将甘特图视图另存为 PDF
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
最后，我们将定制的甘特图视图保存为 PDF 文件。
## 结论
在本教程中，我们学习了如何在 Aspose.Tasks for .NET 中使用甘特图视图。通过遵循提供的步骤，您可以根据您的项目需求有效地操作和自定义甘特图。
## 常见问题解答
### 问：我可以进一步自定义甘特图条形的外观吗？
答：是的，Aspose.Tasks 提供了广泛的选项来自定义甘特图条的外观，包括颜色、形状和大小。
### 问：Aspose.Tasks 是否与不同版本的 Microsoft Project 文件兼容？
答：是的，Aspose.Tasks 支持各种版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。
### 问：我可以将甘特图视图导出为 PDF 以外的格式吗？
答：当然，Aspose.Tasks 支持将甘特图视图导出为多种格式，包括 PNG、JPEG 和 XPS。
### 问：Aspose.Tasks 是否支持复杂的项目调度算法？
答：是的，Aspose.Tasks 提供了先进的调度算法来有效地处理复杂的项目调度。
### 问：是否有社区论坛可供我寻求帮助或分享我使用 Aspose.Tasks 的经验？
答： 是的，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)与其他用户互动、提出问题并找到问题的解决方案。
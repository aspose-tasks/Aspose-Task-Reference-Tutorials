---
title: 在 Aspose.Tasks 中配置甘特图时间刻度层
linktitle: 在 Aspose.Tasks 中配置时间刻度层
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 在甘特图视图中配置时间刻度层，以实现精确的项目时间线可视化。 #Aspose.Tasks #MS 项目
weight: 16
url: /zh/net/text-view-configuration/timescale-tiers/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中配置甘特图时间刻度层

## 介绍
在项目管理的动态环境中，有效的可视化对于理解时间表和截止日期至关重要。 Aspose.Tasks for .NET 提供了强大的工具集，在本教程中，我们将探讨如何配置时间刻度层以在甘特图视图中实现最佳表示。按照这些分步说明来增强您的项目可视化。
## 先决条件
在深入学习本教程之前，请确保您具备以下条件：
- C# 和 .NET 的基础知识。
- 安装了 .NET 库的 Aspose.Tasks。你可以下载它[这里](https://releases.aspose.com/tasks/net/).
- 为 .NET 应用程序开发而设置的开发环境。
## 导入命名空间
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
现在，让我们分解所提供示例的每个步骤。
## 第 1 步：初始化项目并添加任务链接
```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
在这里，我们创建一个项目并在“任务 1”和“任务 2”之间建立任务链接。
## 第 2 步：配置甘特图视图
```csharp
var view = (GanttChartView)project.DefaultView;
```
访问甘特图视图进行自定义。
## 第 3 步：调整中间时间刻度层
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
自定义中间时间刻度层以显示具有特定标签和对齐方式的周。
## 步骤 4：添加顶级时间刻度层
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
添加顶部时间刻度层来表示月份。
## 第 5 步：自定义中间层日期
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
个性化月份标签以获得更好的可视化效果。
## 第 6 步：设定项目时间表
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
定义项目时间表以控制总体时间表。
## 第 7 步：使用自定义时间刻度保存项目
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
使用定义的时间刻度设置保存项目。
## 结论
总之，在 Aspose.Tasks for .NET 中配置时间刻度层可以实现项目时间线的定制化和视觉吸引力的表示。这些步骤使您能够创建精确满足您的项目管理需求的甘特图视图。
## 常见问题解答
### 我可以将 Aspose.Tasks 与其他 .NET 库一起使用吗？
是的，Aspose.Tasks 与其他 .NET 库无缝集成，为您的开发堆栈提供灵活性。
### 临时许可证是否可用于测试目的？
是的，您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/)进行评估。
### 甘特图视图是否有其他自定义选项？
当然，Aspose.Tasks 为甘特图视图提供了广泛的自定义选项，以满足不同的项目需求。
### 我可以以不同的格式渲染时间刻度吗？
当然，您可以探索时间刻度表示的各种格式和样式，以最适合您的项目环境。
### 是否有 Aspose.Tasks 支持的社区论坛？
是的，请访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区支持和讨论。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

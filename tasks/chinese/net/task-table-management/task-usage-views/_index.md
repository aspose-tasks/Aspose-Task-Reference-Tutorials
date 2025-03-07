---
title: 掌握 Aspose.Tasks for .NET 中的任务使用视图
linktitle: 在 Aspose.Tasks 中配置任务使用情况视图
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 并了解如何配置任务使用视图。自定义时间刻度设置并增强您的项目管理视觉效果。
weight: 24
url: /zh/net/task-table-management/task-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握 Aspose.Tasks for .NET 中的任务使用视图

## 介绍
在项目管理领域，可视化任务使用情况对于有效规划和执行至关重要。 Aspose.Tasks for .NET 提供了一个强大的解决方案来渲染任务使用视图，允许您自定义时间刻度设置和演示格式。在本教程中，我们将逐步完成使用 Aspose.Tasks 配置任务使用视图的步骤。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1.  Aspose.Tasks for .NET：确保您已将 Aspose.Tasks 库集成到您的 .NET 项目中。你可以下载它[这里](https://releases.aspose.com/tasks/net/).
2. .NET 环境：在您的计算机上设置有效的 .NET 环境。
## 导入命名空间
在您的 .NET 项目中，导入必要的命名空间以访问 Aspose.Tasks 功能。将以下行添加到您的代码中：
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## 第1步：设置文档目录路径
在使用 Aspose.Tasks 功能之前，请设置文档目录的路径。代替`"Your Document Directory"`与实际路径。
```csharp
String DataDir = "Your Document Directory";
```
## 第 2 步：加载项目
初始化 Aspose.Tasks`Project`通过加载项目文件（例如，TaskUsageView.mpp）来获取对象。
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## 第 3 步：定义保存选项
创建一个`SaveOptions`对象来指定渲染选项。将时间刻度设置为“天”，将演示格式设置为“TaskUsage”。
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## 第 4 步：使用天时间刻度保存
使用预定义的时间刻度设置“天”保存项目。
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 第 5 步：使用 ThirdsOfMonths 时间刻度保存
将时间刻度设置更改为“ThirdsOfMonths”并保存项目。
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 步骤 6：以月为单位进行保存
将时间刻度设置为“月”并使用更新的设置保存项目。
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 结论
使用 Aspose.Tasks for .NET 配置任务使用视图是一个简单的过程。通过自定义时间刻度设置，您可以根据您的特定需求定制项目任务的可视化。
欢迎探索更多特性和功能[文档](https://reference.aspose.com/tasks/net/).
## 经常问的问题
### 我可以自定义超出预定义设置的时间范围吗？
是的，您可以通过指定间隔和单位来设置自定义时间刻度。
### 还有其他可用的演示格式吗？
Aspose.Tasks 支持各种演示格式，包括甘特图、ResourceUsage 等。
### Aspose.Tasks 是否与不同的项目文件格式兼容？
是的，Aspose.Tasks 支持流行的项目文件格式，例如 MPP、XML 和 CSV。
### 我可以对特定任务应用不同的时间刻度设置吗？
当然，您可以为项目中的各个任务自定义时间刻度设置。
### 我如何获得 Aspose.Tasks 的支持或寻求帮助？
参观[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区的支持和指导。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

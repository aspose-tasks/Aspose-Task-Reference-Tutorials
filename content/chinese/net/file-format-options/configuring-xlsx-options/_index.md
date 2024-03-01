---
title: 在 Aspose.Tasks for .NET 中配置 MS Project XLSX 选项
linktitle: 在 Aspose.Tasks 中配置 XLSX 选项
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中配置 MS Project XLSX 选项。轻松自定义列、编码等。
type: docs
weight: 11
url: /zh/net/file-format-options/configuring-xlsx-options/
---
## 介绍
Microsoft Project (MS Project) 是一个强大的项目管理工具，Aspose.Tasks for .NET 提供无缝集成，以便以编程方式处理 MS Project 文件。在本教程中，我们将逐步介绍使用 Aspose.Tasks for .NET 配置 MS Project XLSX 选项的过程。
## 先决条件
在我们开始之前，请确保您具备以下条件：
### 1. Aspose.Tasks for .NET 安装
确保您的开发环境中安装了 Aspose.Tasks for .NET。如果没有，您可以从以下位置下载[Aspose.Tasks for .NET 下载页面](https://releases.aspose.com/tasks/net/).
### 2. 对 C# 和 .NET Framework 的基本了解
需要熟悉 C# 编程语言和 .NET 框架才能学习本教程。
### 3.微软项目文件
准备好要配置并另存为 XLSX 文件的 Microsoft Project 文件 (MPP)。

## 导入命名空间
首先，导入必要的命名空间：
```csharp
    using Aspose.Tasks;
    using System.Text;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```

## 第 1 步：加载项目
```csharp
var project = new Project("YourProjectFile.mpp");
```
加载您要配置的 Microsoft Project 文件。
## 第 2 步：定义 XlsxOptions
```csharp
var options = new XlsxOptions();
```
创建一个实例`XlsxOptions`配置保存为 XLSX 的设置。
## 第 3 步：添加甘特图列
```csharp
var col = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(col);
```
将所需的甘特图列添加到选项中。
## 步骤 4：添加资源视图列
```csharp
var rscCol = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(rscCol);
```
在选项中包含资源视图所需的列。
## 第 5 步：添加作业视图列
```csharp
var assnCol = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assnCol);
```
在选项中为分配视图添加所需的列。
## 第6步：设置编码
```csharp
options.Encoding = Encoding.Unicode;
```
设置输出文件的编码。
## 第 7 步：将项目另存为 XLSX
```csharp
project.Save("OutputFile.xlsx", options);
```
将具有配置选项的项目保存为 XLSX 文件。

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 配置 MS Project XLSX 选项。通过执行以下步骤，您可以根据您的要求自定义输出格式，从而增强项目管理工作流程的灵活性和可用性。
## 常见问题解答

### 问：我可以为甘特图、资源视图和作业视图分别配置不同的列吗？

答：是的，您可以使用 Aspose.Tasks for .NET 为每个视图独立自定义列。

### 问：购买 Aspose.Tasks for .NET 之前是否有试用版？

答：是的，您可以从以下网站下载免费试用版：[Aspose.Tasks for .NET 发布页面](https://releases.aspose.com/).

### 问：如果我在实施过程中遇到任何问题或疑问，如何获得支持？

答：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)寻求社区和 Aspose 支持团队的帮助。

### 问：我可以在非 Windows 平台上使用 Aspose.Tasks for .NET 生成 XLSX 文件吗？

答：Aspose.Tasks for .NET 主要是为 Windows 平台设计的，但您可以探索其他平台的兼容性选项。

### 问：是否有任何临时许可证选项可用于测试目的？

答：是的，您可以从以下机构获得临时许可证：[Aspose.Tasks 临时许可证页面](https://purchase.aspose.com/temporary-license/).
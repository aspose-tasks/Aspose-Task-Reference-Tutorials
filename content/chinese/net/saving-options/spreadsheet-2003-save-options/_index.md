---
title: MS Project 与 Aspose.Tasks 的 Spreadsheet 2003 选项
linktitle: Spreadsheet 2003 Aspose.Tasks 的保存选项
second_title: Aspose.Tasks .NET API
description: Master Spreadsheet 2003 使用 Aspose.Tasks for .NET 保存 MS 项目选项。以编程方式无缝自定义和保存 MS Project 文件。
type: docs
weight: 19
url: /zh/net/saving-options/spreadsheet-2003-save-options/
---
## 介绍
在本教程中，我们将深入研究如何利用 Aspose.Tasks for .NET 来利用 Spreadsheet 2003 Save MS Project Options。这个强大的工具允许在 .NET 环境中无缝操作和自定义 MS Project 文件。让我们逐步分解该过程。
## 先决条件
在开始本教程之前，请确保您满足以下先决条件：
1. 安装 Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET 库：[下载链接](https://releases.aspose.com/tasks/net/).
2. 熟悉 C# 编程：要掌握本教程中讨论的概念，需要对 C# 编程语言有基本的了解。

## 导入命名空间
首先将必要的命名空间导入到您的 C# 项目中：
```csharp
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
这些命名空间提供对使用 Spreadsheet 2003 格式保存 MS Project 文件和自定义视图选项所需的功能的访问。
## 第 1 步：加载项目
首先，使用 Aspose.Tasks 加载 MS Project 文件：
```csharp
var project = new Project(DataDir + "CreateProject2.mpp");
```
代替`"Your Document Directory"`与您的 MS Project 文件所在的实际目录路径。
## 第 2 步：定义保存选项
通过创建实例来定义 Spreadsheet 2003 保存选项`Spreadsheet2003SaveOptions`,
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## 第 3 步：自定义视图列
自定义甘特图、资源视图和作业视图的视图列：
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
这些步骤将自定义列添加到相应的视图中，从而增强 MS Project 文件的可视化和分析功能。
## 第 4 步：保存项目
最后，使用指定的选项保存项目：
```csharp
project.Save(DataDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```
此命令以 Spreadsheet 2003 格式和自定义视图列保存修改后的项目。

## 结论
利用Aspose.Tasks for .NET，特别是Spreadsheet 2003 Save MS Project Options，使开发人员能够以编程方式有效地管理和自定义MS Project 文件。通过遵循本教程中概述的分步指南，您可以将这些功能无缝集成到您的 .NET 应用程序中，从而提高工作效率和灵活性。

## 常见问题解答
### 问：Aspose.Tasks for .NET 可以在 Web 和桌面应用程序中使用吗？
答：是的，Aspose.Tasks for .NET 可以无缝集成到 Web 和桌面应用程序中，提供跨平台的一致功能。
### 问：Aspose.Tasks for .NET 有试用版吗？
答：是的，您可以从以下位置访问 Aspose.Tasks for .NET 的免费试用版：[网站](https://releases.aspose.com/)，让您可以在购买前探索其功能。
### 问：使用 Aspose.Tasks for .NET 自定义视图列有什么限制吗？
答：Aspose.Tasks for .NET 为视图列提供了广泛的自定义选项，且限制极小。然而，复杂的定制可能需要对库有深入的了解。
### 问：如果在使用 Aspose.Tasks for .NET 时遇到问题，我可以寻求帮助吗？
答：当然！您可以在 Aspose.Tasks 论坛上找到全面的支持和资源：[https://forum.aspose.com/c/tasks/15](https://forum.aspose.com/c/tasks/15)，专家和社区成员可以帮助解决您可能面临的任何疑问或挑战。
### 问：如何获得 Aspose.Tasks for .NET 的临时许可证？
答：您可以从 Aspose.Tasks for .NET 获取临时许可证。[购买页面](https://purchase.aspose.com/temporary-license/)，使您能够评估库的全部功能。
---
title: 掌握 Aspose.Tasks 的 MS Project 保存选项
linktitle: Aspose.Tasks 的常规保存选项
second_title: Aspose.Tasks .NET API
description: 了解使用 Aspose.Tasks for .NET 高效保存 MS Project 文件。轻松为您的项目自定义输出选项。
type: docs
weight: 17
url: /zh/net/saving-options/general-save-options/
---
## 介绍
Aspose.Tasks for .NET 提供了以编程方式操作 Microsoft Project 文件的强大功能。在本教程中，我们将深入研究使用 Aspose.Tasks 提供的各种选项保存 MS Project 文件的复杂性。具体来说，我们将重点关注 Aspose.Tasks 可用的一般保存选项，允许您根据您的特定要求定制输出。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：
1. 安装 Aspose.Tasks for .NET：从以下位置下载并安装 Aspose.Tasks for .NET[下载链接](https://releases.aspose.com/tasks/net/).
2. 对 .NET Framework 的基本了解：熟悉 .NET 编程概念是有益的。

## 导入命名空间
在深入代码之前，请确保导入必要的名称空间：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## 第 1 步：加载项目文件
首先，您需要使用 Aspose.Tasks 加载 MS Project 文件：
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## 第 2 步：定义保存选项
根据您的要求定义保存选项。在此示例中，我们使用`Spreadsheet2003SaveOptions`,
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## 第 3 步：自定义视图列
您可以自定义视图列，例如甘特图、资源视图和分配视图。以下是向每个添加列的方法：
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## 第 4 步：使用选项保存项目
最后，使用指定的选项保存项目：
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 结论
使用 Aspose.Tasks for .NET 掌握一般的 MS Project 保存选项，使您能够根据项目的需求有效地自定义输出格式。
## 常见问题解答
### 问：Aspose.Tasks 是否与不同版本的 MS Project 文件兼容？
答：是的，Aspose.Tasks 支持各种版本的 MS Project 文件，确保不同环境之间的兼容性。
### 问：我可以在购买前试用 Aspose.Tasks 吗？
答：是的，您可以通过免费试用版探索 Aspose.Tasks[这里](https://releases.aspose.com/).
### 问：在哪里可以找到 Aspose.Tasks 的文档？
答：详细的文档可以找到[这里](https://reference.aspose.com/tasks/net/)，提供有关使用 Aspose.Tasks 功能的全面指导。
### 问：如何获得 Aspose.Tasks 的临时许可证？
答：临时许可证可用于评估目的。[这里](https://purchase.aspose.com/temporary-license/).
### 问：我在哪里可以寻求 Aspose.Tasks 相关查询的支持？
答：您可以加入Aspose.Tasks社区论坛[这里](https://forum.aspose.com/c/tasks/15)获得专家和其他开发人员的帮助。
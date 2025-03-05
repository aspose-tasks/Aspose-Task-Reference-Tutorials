---
title: 自定义 Aspose.Tasks 中的 MS Project 资源视图列
linktitle: 在 Aspose.Tasks 中自定义资源视图列
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效地自定义 MS Project 资源视图列。创建定制视图以实现更好的项目管理。
type: docs
weight: 17
url: /zh/net/resource-risk-analysis/resource-view-columns/
---
## 介绍
Aspose.Tasks for .NET 是一个功能强大的 API，允许开发人员以编程方式处理 Microsoft Project 文件。项目管理中的一项常见任务是自定义视图以显示特定信息。在本教程中，我们将探索如何使用 Aspose.Tasks for .NET 自定义 MS Project 资源视图列。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1.  Aspose.Tasks for .NET Library：您可以从以下位置下载它[这里](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 文件：准备一个示例 MS Project 文件以供测试。
3. 开发环境：采用.NET框架搭建的开发环境。
## 导入命名空间
首先，让我们将必要的命名空间导入到我们的项目中：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## 第 1 步：加载项目文件
使用 Aspose.Tasks API 加载 MS Project 文件：
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## 第 2 步：获取资源并定义选项
接下来，获取要自定义其视图列的资源并定义 PDF 保存选项：
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## 第 3 步：定义自定义列
现在，为资源视图定义自定义列。您可以指定各种字段，甚至使用委托进行自定义计算：
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## 第 4 步：迭代列
迭代定义的列并显示它们的属性：
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## 第 5 步：保存自定义视图
最后，设置自定义视图并将其保存为 PDF 文件：
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
通过执行这些步骤，您可以使用 Aspose.Tasks for .NET 高效地自定义 MS Project 资源视图列。
## 结论
自定义 MS Project 资源视图列对于显示根据项目需求定制的相关信息至关重要。借助 Aspose.Tasks for .NET，此任务变得简单而高效，让您可以轻松创建自定义视图。
## 常见问题解答
### 除了资源之外，我可以自定义其他元素的视图吗？
是的，Aspose.Tasks 还允许自定义任务、分配和其他项目元素。
### Aspose.Tasks 是否支持以 PDF 以外的格式保存视图？
是的，您可以以各种格式保存视图，例如 XLSX、HTML 和图像。
### 是否可以将格式应用于自定义视图？
当然，Aspose.Tasks 提供了广泛的格式化选项来增强自定义视图的外观。
### 我可以根据更改的项目数据动态更新自定义视图吗？
是的，只要基础项目数据发生变化，您就可以更新并重新生成自定义视图。
### Aspose.Tasks支持跨平台开发吗？
Aspose.Tasks for .NET 主要针对 .NET 平台，但也有适用于 Java 和其他平台的版本。
---
title: Aspose.Tasks 中的自定义分配视图列
linktitle: Aspose.Tasks 中的自定义分配视图列
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中添加自定义分配视图列以增强项目管理功能。
type: docs
weight: 16
url: /zh/net/advanced-features/assignment-view-column/
---
## 介绍

在本教程中，我们将探索如何使用 Aspose.Tasks for .NET 为作业视图添加自定义列。自定义列提供了灵活性，并允许您显示与项目管理需求相关的附加信息。

## 先决条件

在我们开始之前，请确保您具备以下条件：

1. C# 编程语言的基础知识。
2. 安装了 .NET 库的 Aspose.Tasks。如果没有的话可以下载[这里](https://releases.aspose.com/tasks/net/).
3. 集成开发环境 (IDE)，例如 Visual Studio。

## 导入命名空间

首先，让我们导入必要的命名空间来访问创建自定义分配视图列所需的类和方法：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 第 1 步：加载项目

首先，使用以下命令加载您的项目文件`Project`班级：

```csharp
//文档目录的路径。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## 第 2 步：创建电子表格保存选项

接下来，创建一个实例`Spreadsheet2003SaveOptions`这允许我们自定义分配视图列：

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## 第 3 步：定义自定义列

现在，通过创建一个实例来定义您的自定义列`AssignmentViewColumn`。该类需要列名、宽度和委托函数来将赋值数据转换为列文本：

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## 第 4 步：将自定义列添加到选项

将自定义列添加到保存选项的分配视图列集合中：

```csharp
options.AssignmentView.Columns.Add(column);
```

## 第 5 步：迭代分配

迭代项目中的每个资源分配并显示自定义列文本：

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## 第 6 步：使用自定义列保存项目

最后，使用自定义分配视图列保存项目：

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Tasks for .NET 添加自定义分配视图列。自定义列可以灵活地显示根据您的项目要求定制的附加信息，从而增强项目管理能力。

## 常见问题解答

### Q1：我可以向作业视图添加多个自定义列吗？

 A1：是的，您可以通过创建额外的实例来添加多个自定义列`AssignmentViewColumn`并将它们添加到`Columns`收藏。

### Q2：是否有可用于常见分配字段的预定义转换器？

A2：是的，Aspose.Tasks 为常见分配字段提供了预定义的转换器，使提取自定义列的数据变得更加容易。

### 问题 3：我可以自定义自定义列的外观，例如格式化文本或应用样式吗？

A3：是的，您可以通过修改宽度、字体和对齐方式等属性来自定义自定义列的外观。

### 问题 4：是否可以从分配视图中删除默认列？

 A4：是的，您可以通过将默认列从列表中排除来删除它们`Columns`集合或将其宽度设置为零。

### Q5：除了带有自定义列的电子表格之外，Aspose.Tasks 是否支持将项目导出为其他格式？

A5：是的，Aspose.Tasks 支持将项目导出为各种格式，例如 PDF、HTML 和 XML，从而提供多种项目报告选项。
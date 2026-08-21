---
date: 2026-03-19
description: 了解如何在使用 Aspose.Tasks for .NET 将项目导出为 XML 时添加多个自定义列并设置自定义列宽。
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 中向分配视图添加多个自定义列
url: /zh/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中向任务分配视图添加多个自定义列

## Introduction

在本教程中，您将了解 **如何向 Aspose.Tasks for .NET 的任务分配视图添加多个自定义列**。自定义列允许您在导出报告中直接显示额外数据——例如备注、成本或自定义标记。通过本指南，您将能够设置自定义列宽度、将项目导出为 XML，并根据项目管理需求定制视图。

## Quick Answers
- **What can I achieve?** 在自定义列中显示任何任务分配数据并控制其外观。  
- **Which format supports it?** 使用 `Spreadsheet2003SaveOptions` 将项目导出为 XML（或其他格式）。  
- **Do I need a license?** 是的，生产环境需要有效的 Aspose.Tasks 许可证。  
- **Which .NET versions work?** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **How many columns can I add?** 无限——只需创建额外的 `AssignmentViewColumn` 实例。

## What are multiple custom columns?
多个自定义列是用户定义的字段，在项目保存或导出时会出现在默认任务分配列旁边。它们让您能够展示 `ResourceAssignment` 对象的任意属性，例如自定义备注、成本代码或计算值。

## Why add multiple custom columns to the assignment view?
- **Enhanced reporting:** 包含内置列未覆盖的项目特定信息。  
- **Better decision‑making:** 利益相关者无需深入原始文件即可看到所需的精确数据。  
- **Consistent formatting:** 控制列宽和文本转换，获得整洁、易读的输出。  

## Prerequisites

在开始之前，请确保您已具备以下条件：

1. 基本的 C# 编程语言知识。  
2. 已安装 Aspose.Tasks for .NET 库。如未安装，可在 **[此处](https://releases.aspose.com/tasks/net/)** 下载。  
3. 如 Visual Studio 等集成开发环境（IDE）。

## Step-by-Step Guide

### Step 1: Import Namespaces
首先，导入提供处理项目和可视化所需类的命名空间。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Step 2: Load the Project
创建 `Project` 实例并加载已有的 MPP 文件。

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Step 3: Create Spreadsheet Save Options
实例化 `Spreadsheet2003SaveOptions` —— 该对象允许我们在导出前自定义任务分配视图。

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Step 4: Define Custom Column
为每个想要显示的数据创建 `AssignmentViewColumn`。下面我们添加一个宽度为 200 点的 **Notes** 列。

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tip:** 若要添加*多个*自定义列，请使用不同的字段名称和委托逻辑重复此步骤，然后将每个实例添加到 `options.AssignmentView.Columns`。

### Step 5: Add Custom Column to Options
将列（或多列）添加到任务分配视图的 `Columns` 集合中。

```csharp
options.AssignmentView.Columns.Add(column);
```

### Step 6: Iterate Through Assignments (Optional Debugging)
您可以遍历任务分配，以验证自定义列文本是否正确生成。

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

### Step 7: Save the Project with Custom Columns
最后，保存项目。示例保存为 XML，但您可以选择任何受支持的格式。

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## How to export project to XML with custom columns?
如何使用自定义列将项目导出为 XML？当您使用配置好的 `Spreadsheet2003SaveOptions` 调用 `project.Save` 时，Aspose.Tasks 会将项目数据（包括所有 **多个自定义列**）写入所选的 XML 文件。这使得将丰富的项目信息与其他系统或利益相关者共享变得轻松。

## Format custom column width for better readability
为获得更好可读性而设置自定义列宽度  
`AssignmentViewColumn` 构造函数的第二个参数控制列宽（以点为单位）。根据预期的文本量调整此值。例如，宽度 **300** 适用于较长的备注，而 **100** 足以显示短标记。

## Common Issues and Solutions
- **Column text appears blank:** 确保委托返回字符串且底层任务分配属性（如 `Asn.NotesText`）已填充。  
- **Columns are not visible in the exported file:** 在调用 `Save` 前确认 `options.AssignmentView.Columns` 包含您的自定义列。  
- **Width seems ignored:** 某些导出格式有自己的布局规则；XML 会遵守宽度设置，但 PDF/HTML 可能需要额外的样式。

## Frequently Asked Questions

### Q1: 我可以向任务分配视图添加多个自定义列吗？
**A:** 可以，只需创建额外的 `AssignmentViewColumn` 对象并将每个添加到 `options.AssignmentView.Columns`。

### Q2: 是否有针对常见任务分配字段的预定义转换器？
**A:** 有，Aspose.Tasks 为许多标准字段提供内置转换器，无需编写自定义委托即可轻松获取数据。

### Q3: 我可以自定义自定义列的外观吗，例如格式化文本或应用样式？
**A:** 当然。除了设置宽度外，您还可以通过列的样式选项修改字体、对齐方式和其他视觉属性。

### Q4: 能否从任务分配视图中移除默认列？
**A:** 可以通过从 `Columns` 集合中移除默认列或将其宽度设为零来排除默认列。

### Q5: Aspose.Tasks 是否支持将项目导出为除带自定义列的电子表格之外的其他格式？
**A:** 支持，Aspose.Tasks 可以导出为 PDF、HTML、XML 以及许多其他格式，同时保留自定义列定义。

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
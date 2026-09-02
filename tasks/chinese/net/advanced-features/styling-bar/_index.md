---
date: 2026-04-06
description: 了解如何在 Aspose.Tasks for .NET 中更改条形样式并自定义条形颜色，以增强项目可视化。
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Aspose.Tasks 中的样式栏
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中更改条形样式
url: /zh/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中更改条形样式

## 介绍

如果您需要在 Microsoft Project 文件中 **更改条形** 外观，Aspose.Tasks for .NET 为您提供对条形颜色、形状和文本样式的完整控制。通过自定义条形颜色和其他视觉属性，您可以让项目计划更易于阅读，并更符合组织的品牌形象。在本教程中，我们将通过一个完整的逐步示例，展示如何更改条形样式，从加载项目到导出并应用新的视觉规则。

## 快速答案
- **我可以样式化什么？** 条形、里程碑和甘特图中的任务文本。  
- **哪种格式支持样式化的条形？** PDF、XLSX、HTML，以及使用 `PdfSaveOptions` 保存时的原生 MPP。  
- **我需要许可证吗？** 生产使用需要商业许可证；免费试用可用于测试。  
- **我可以应用多个样式吗？** 可以——根据需要添加任意数量的 `BarStyle` 对象。  
- **它兼容 .NET Core 吗？** 完全兼容——可在 .NET Framework 和 .NET Core/5/6+ 上运行。

## 什么是 Aspose.Tasks 中的条形样式？

条形样式允许您定义在渲染甘特图时 Aspose.Tasks 引擎应用的视觉规则。每条规则（即 **BarStyle**）针对特定的项目类型——任务、里程碑或汇总任务，并允许您设置颜色、形状，甚至自定义文本。

## 为什么要自定义条形颜色？

自定义条形颜色可帮助利益相关者快速识别关键路径、延迟任务或里程碑。它还可以让您匹配企业配色方案，使报告看起来专业且符合品牌形象。

## 前提条件

1. **Aspose.Tasks for .NET** – 从[下载页面](https://releases.aspose.com/tasks/net/)下载。  
2. 支持 .NET 的开发环境（Framework 4.6+、.NET Core 3.1+ 或更高版本）。  
3. 对 C# 有基本了解——示例使用简单、独立的代码。

## 导入命名空间

首先，导入包含我们将使用的类的命名空间：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 步骤 1：加载项目

加载现有的 MPP 文件（或创建一个新文件），以便获得可操作的项目对象：

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## 步骤 2：配置保存选项

创建 `PdfSaveOptions` 实例并初始化 `BarStyles` 集合，以存放我们的自定义样式：

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## 步骤 3：定义条形样式

现在我们构建一个 `BarStyle` 对象并设置控制条形外观的属性。这就是我们 **自定义条形颜色** 和形状的地方：

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## 步骤 4：自定义文本转换器（可选）

如果您想调整条形上显示的文本，可以分配自定义转换器。示例为未以 “T” 开头的任务名称添加前缀：

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## 步骤 5：将条形样式添加到选项中

将完整配置的样式添加到保存选项的 `BarStyles` 集合中：

```csharp
options.BarStyles.Add(style);
```

## 步骤 6：保存项目

最后，导出项目。PDF（或其他格式）将使用我们定义的条形样式渲染甘特图：

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **未应用条形样式** | `BarStyles` 集合为空或未附加到保存选项。 | 在调用 `Save` 之前，确保已将 `BarStyle` 添加到 `options.BarStyles`。 |
| **PDF 中颜色显示不同** | PDF 渲染可能使用不同的颜色配置文件。 | 使用标准的 `System.Drawing.Color` 值或定义自定义 ARGB 颜色。 |
| **文本转换器抛出空引用异常** | 某些任务的属性 `Tsk.Name` 为 null。 | 在访问 `task.Get(Tsk.Name)` 之前添加空值检查。 |

## 常见问题

### Q1：我可以对单个项目应用多个条形样式吗？

A1：是的，您可以在同一项目中为不同类型的任务定义并应用多个条形样式。

### Q2：是否可以在运行时动态更改条形样式？

A2：是的，您可以根据特定条件或用户偏好在应用程序中动态修改条形样式。

### Q3：Aspose.Tasks 是否支持将带有样式化条形的项目导出为不同的文件格式？

A3：是的，Aspose.Tasks 支持将带有样式化条形的项目导出为多种格式，如 PDF、XLSX 和 HTML。

### Q4：Aspose.Tasks 是否提供预定义的条形样式？

A4：虽然 Aspose.Tasks 提供默认的条形样式，开发者也可以创建符合项目需求的自定义条形样式。

### Q5：我可以使用 API 检索并修改项目中已有的条形样式吗？

A5：是的，您可以使用 Aspose.Tasks for .NET API 以编程方式检索和修改已有的条形样式。

## 常见问答

**问：如何为普通任务而不是里程碑更改条形颜色？**  
答：将 `style.ItemType = BarItemType.Task;` 并将 `style.BarColor` 设置为所需的 `Color`。

**问：我可以在导出为 HTML 时使用此方法对条形进行样式化吗？**  
答：可以。使用 `HtmlSaveOptions` 并以相同方式填充其 `BarStyles` 集合。

**问：我可以定义的条形样式数量是否有限制？**  
答：实际上没有限制；您可以根据需要添加任意数量，但对于非常大的集合请注意性能。

**问：更改样式后是否需要调用 `project.Calculate()`？**  
答：不需要，样式在保存操作期间应用；仅在日程更改时才需要重新计算。

---

**最后更新：** 2026-04-06  
**测试环境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-03-08
description: 学习如何使用 Aspose.Tasks for .NET 在项目管理中设置标签显示并自定义天标签，以提升可读性和清晰度。
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks for .NET 中设置标签显示
url: /zh/net/advanced-concepts/label-display/
weight: 14
---

 craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for .NET 中设置标签显示

## 介绍

在使用 **Aspose.Tasks for .NET** 构建项目管理解决方案时，能够 **设置标签** 选项对于让进度表易于阅读至关重要。无论您需要分钟级的精确度还是年度层面的宏观视图，自定义标签显示都能让您以利益相关者期望的方式呈现时间线。在本教程中，我们将逐步演示如何为分钟、小时、天、周、月和年设置标签显示，并展示如何 **自定义天标签** 格式以获得最佳清晰度。

## 快速答案
- **“设置标签”是什么意思？** 它指的是配置控制项目文件中时间单位显示方式的 `DisplayOptions` 属性。  
- **我可以更改哪些标签？** 分别可以配置分钟、小时、天、周、月和年。  
- **需要许可证吗？** 生产环境需要有效的 Aspose.Tasks 许可证；免费试用版可用于测试。  
- **在 .NET Core 上支持吗？** 是的，API 可在 .NET Core、.NET 5/6 以及完整的 .NET Framework 上使用。  
- **可以在运行时更改标签吗？** 完全可以——在保存项目之前随时修改显示选项。

## 什么是 Aspose.Tasks 中的标签显示？

标签显示决定了甘特图和时间尺度上时间单位（分钟、小时、天等）的文本表现形式。通过设置相应的 `DisplayOptions` 属性，您可以指示 Aspose.Tasks 如何渲染这些单位，从而显著提升项目的可读性。

## 为什么要自定义标签显示？

- **提升可读性：** 利益相关者能够瞬间把握进度的粒度。  
- **报告一致性：** 将视觉输出与企业标准对齐（例如使用 “Mo” 表示月份）。  
- **灵活性：** 在详细视图和宏观视图之间切换，而无需更改底层进度数据。

## 前置条件

1. **C# 知识** – 对 C# 语法和 .NET 项目结构有基本了解。  
2. **Aspose.Tasks for .NET** – 从 [here](https://releases.aspose.com/tasks/net/) 下载并安装库。  
3. **开发环境** – Visual Studio、VS Code 或任何支持 .NET 开发的 IDE。

## 导入命名空间

在开始之前，导入所需的命名空间：

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## 如何为分钟设置标签显示

### 1. 显示分钟标签

要设置分钟标签，请使用 `MinuteLabel` 属性：

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## 如何为小时设置标签显示

### 2. 显示小时标签

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## 自定义天标签显示

### 3. 显示天标签

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## 如何为周设置标签显示

### 4. 显示周标签

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## 如何为月设置标签显示

### 5. 显示月标签

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## 如何为年设置标签显示

### 6. 显示年标签

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## 常见陷阱与技巧

- **技巧：** 始终在保存项目之前设置标签显示；保存后再修改的更改不会体现在文件中。  
- **陷阱：** 使用不受支持的枚举值会抛出 `ArgumentException`。请使用提供的 `*LabelDisplay` 枚举。  
- **技巧：** 如果需要为不同视图使用不同的标签样式，可创建独立的 `Project` 实例或克隆 `DisplayOptions` 对象。

## 结论

通过掌握 **设置标签** 选项，您可以对项目进度的视觉呈现进行细粒度控制。无论是为每日站会板自定义天标签，还是为多年度路线图调整年标签，这些设置都能帮助您交付更清晰、更专业的项目文档。

## 常见问题

### Q1: 我可以为项目的特定部分自定义标签显示吗？

A1: 可以，Aspose.Tasks for .NET 允许对项目的特定部分进行细粒度的标签显示控制，以满足个性化需求。

### Q2: Aspose.Tasks 是否兼容常见的 .NET 框架？

A2: 是的，Aspose.Tasks for .NET 兼容多种 .NET 框架，包括 .NET Core 和 .NET Framework。

### Q3: 我可以根据项目需求动态更改标签显示吗？

A3: 完全可以，Aspose.Tasks for .NET 的灵活性使您能够根据项目需求的变化动态调整标签显示。

### Q4: 标签显示的自定义是否有限制？

A4: Aspose.Tasks for .NET 提供了丰富的标签显示自定义选项，限制极少，为用户提供了充足的灵活性。

### Q5: Aspose.Tasks 是否支持与其他项目管理工具集成？

A5: 支持，Aspose.Tasks 提供无缝的集成能力，便于与其他项目管理工具和平台进行互操作。

---

**最后更新:** 2026-03-08  
**测试版本:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
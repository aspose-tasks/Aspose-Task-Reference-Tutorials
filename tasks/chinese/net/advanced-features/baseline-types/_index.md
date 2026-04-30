---
date: 2026-04-30
description: 学习如何使用 Aspose.Tasks for .NET 设置基准并高效地操作项目基准。
keywords:
- how to set baseline
- track project progress
- baseline vs actual schedule
- set project baseline
- manage project baselines
linktitle: Aspose.Tasks 中的不同基线类型
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中设置基准 – 不同的基准类型
url: /zh/net/advanced-features/baseline-types/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中不同类型的基线

## 介绍

在项目管理中，**如何正确设置基线** 可以决定项目是保持进度还是失控。Aspose.Tasks for .NET 为您提供功能完整的 API，用于创建、更新和比较基线，让您能够 **跟踪项目进度** 与原始计划进行对比。在本教程中，您将学习如何设置基线、使用多种基线类型，并利用这些数据分析项目的 **基线与实际进度**。

## 快速答案
- **What is a baseline?** 在项目的特定时间点拍摄的进度、成本和工作数据的快照。  
- **How many baselines can Aspose.Tasks store?** 每个项目最多可存储 11 个不同的基线。  
- **Why set a baseline?** 用于将实际表现与原始计划进行比较并识别差异。  
- **Do I need a license to try this?** 提供免费试用；生产环境需要许可证。  
- **Which .NET versions are supported?** 支持 .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 在 Aspose.Tasks 中，“如何设置基线” 是什么？
设置基线是指在 `Project` 对象上调用 `SetBaseline` 方法。该 API 允许您从多个 `BaselineType` 值（Baseline、Baseline1 … Baseline10）中选择，以便在项目演进过程中保留历史快照。

## 为什么要管理项目基线？
- **Measure variance:** 快速查看任务是提前还是落后于计划。  
- **Cost control:** 将基线成本与实际支出进行比较。  
- **Stakeholder reporting:** 将基线数据导出为 PDF、XLSX 或其他格式，以便清晰沟通。  
- **Scenario planning:** 存储多个基线以评估 “假设” 调度。

## 先决条件

### 1. 熟悉 C# 和 .NET Framework
需要对 C# 类、方法以及面向对象概念有基本了解。

### 2. 安装 Aspose.Tasks for .NET
确保已将该库添加到项目中。您可以从 [Aspose.Tasks 网站](https://releases.aspose.com/tasks/net/) 下载，或通过 NuGet 安装。

### 3. 集成开发环境 (IDE)
推荐使用 Visual Studio（或任何兼容的 IDE）来编写、编译和调试 C# 代码。

## 导入命名空间

在我们的 C# 项目中使用 Aspose.Tasks 之前，需要导入必要的命名空间以访问所需的类和方法。请按以下步骤操作：

```csharp

```

现在我们已经完成先决条件的设置并导入了必要的命名空间，让我们深入使用 Aspose.Tasks for .NET 设置不同类型的基线。我们将把每个示例拆分为多个步骤，以便更清晰、更易于理解。

## 如何在 Aspose.Tasks 中设置基线

### 步骤 1：加载项目文件
首先，需要加载要设置基线的项目文件。此步骤涉及初始化 `Project` 对象并加载项目文件。下面演示如何操作：

```csharp
var project = new Project("Project2.mpp");
```

### 步骤 2：设置基线
项目加载后，我们即可设置基线。基线提供了项目初始进度的快照，作为项目推进过程中进行比较的参考点。使用 `SetBaseline` 方法来设置基线。例如，要为整个项目设置基线，可使用 `BaselineType.Baseline` 枚举：

```csharp
project.SetBaseline(BaselineType.Baseline);
```

### 步骤 3：使用项目基线
设置基线后，您可以使用各种项目基线字段来准确分析和跟踪项目进度。此步骤涉及访问基线数据，如开始日期、完成日期、持续时间和成本。在这里，您可以利用 Aspose.Tasks 提供的丰富功能，根据需求操作基线数据。

## 常见问题及解决方案
- **Baseline not applied:** 确保在调用 `SetBaseline` 后保存项目文件。如需持久化更改，请使用 `project.Save("output.mpp");`。  
- **Multiple baselines conflict:** 设置多个基线时，请指定正确的 `BaselineType`（例如 `Baseline1`、`Baseline2`）。  
- **Version mismatch:** 验证 Aspose.Tasks DLL 版本与目标 .NET 运行时匹配。

## 常见问答

**Q: 我可以在单个项目中使用 Aspose.Tasks for .NET 设置多个基线吗？**  
A: 可以，Aspose.Tasks 允许为项目设置最多 11 条基线，提供全面的跟踪能力。

**Q: Aspose.Tasks 是否兼容不同的项目文件格式？**  
A: 当然！Aspose.Tasks 支持多种项目文件格式，如 MPP、XML 和 MPX，确保在不同平台上的兼容性。

**Q: 我如何在项目中可视化基线数据？**  
A: 您可以使用 Aspose.Tasks 将项目数据导出为常用文件格式，如 PDF 或 XLSX，以便轻松可视化和共享基线信息。

**Q: Aspose.Tasks 是否提供与项目管理工具集成的支持？**  
A: Aspose.Tasks 提供丰富的文档和支持论坛，帮助开发者将其功能无缝集成到流行的项目管理工具和平台中。

**Q: 我可以在购买前试用 Aspose.Tasks 吗？**  
A: 可以，您可以通过网站提供的免费试用来体验 Aspose.Tasks 的功能。

---

**最后更新：** 2026-04-30  
**测试环境：** Aspose.Tasks for .NET (latest stable release)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
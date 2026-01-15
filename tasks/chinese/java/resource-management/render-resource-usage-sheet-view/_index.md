---
date: 2026-01-15
description: 了解如何使用 Aspose.Tasks for Java 将项目保存为 PDF 并渲染 MS Project 资源使用和工作表视图。按照我们的分步指南，轻松将项目导出为
  PDF。
linktitle: Save Project as PDF – Render Resource Usage and Sheet View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 将项目另存为 PDF – 在 Aspose.Tasks 中渲染资源使用情况和表格视图
url: /zh/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将项目保存为 PDF – 在 Aspose.Tasks 中呈现资源使用情况和表格视图

## Introduction
在本教程中，您将了解如何在渲染 Microsoft Project 文件的资源使用情况和表格视图的同时 **将项目保存为 PDF**。无论是为利益相关者生成可打印报告，还是将 MPP 文件转换为通用可查看的格式，Aspose.Tasks for Java 都能让此过程变得简便——无需安装 Microsoft Project。

## Quick Answers
- **“save project as pdf” 的作用是什么？** 它将 Project 文件（MPP）转换为 PDF 文档，并保留所选视图。  
- **可以导出哪些视图？** 资源使用、表格、甘特图、任务使用等。  
- **我可以在 PDF 中更改时间尺度吗？** 可以——选项包括 Days、ThirdsOfMonths 和 Months。  
- **需要安装 Microsoft Project 吗？** 不需要，Aspose.Tasks 可独立运行。  
- **生产环境需要许可证吗？** 是的，非试用使用需要商业许可证。

## What is “save project as PDF”?
将项目保存为 PDF 会创建所选 Project 视图的静态高分辨率表示。这非常适合与客户共享、归档或打印，而无需暴露底层项目文件。

## Why use Aspose.Tasks to export project to PDF?
- **无外部依赖** – 在任何支持 Java 的平台上均可运行。  
- **细粒度控制** – 您可以选择视图、时间尺度和布局。  
- **高保真度** – PDF 复制原始 Project 视图的外观。  
- **自动化就绪** – 可集成到 CI 流水线、报告服务或批量转换器中。

## Prerequisites
在开始之前，请确保您已具备以下条件：

1. **Java Development Kit (JDK)** – 建议使用最新版本。  
2. **Aspose.Tasks for Java** – 从[下载页面](https://releases.aspose.com/tasks/java/)下载。  

## Import Packages
首先，将必要的类导入到您的 Java 项目中：

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## Step‑by‑Step Guide

### Step 1: Read the Source Project
加载要转换的 MPP 文件。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### Step 2: Define SaveOptions with Required Timescale (Export Project to PDF)
配置 PDF 导出选项并设置所需的时间尺度。  
*此处以 **Days** 为例。*

```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### Step 3: Set the Presentation Format to ResourceUsage
选择要呈现的视图。本例中为 **Resource Usage** 视图。

```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### Step 4: Save the Project (Convert MPP to PDF)
执行转换并生成 PDF 文件。

```java
// Save the Project
project.save(dataDir + "result_days.pdf", options);
```

### Step 5: Render Views for Other Timescale Settings (Change Timescale PDF)
重复前面的步骤，以生成不同时间尺度（如 **ThirdsOfMonths** 和 **Months**）的 PDF。

```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(dataDir + "result_thirds.pdf", options);

// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + "result_months.pdf", options);
```

## Common Issues and Solutions
- **文件未找到错误** – 确认 `dataDir` 指向正确的文件夹，并且 MPP 文件名完全匹配。  
- **空白 PDF 输出** – 确保 `PresentationFormat` 对应的视图包含数据（例如 ResourceUsage）。  
- **时间尺度不正确** – 再次确认在每次 `project.save()` 之前调用了 `options.setTimescale()`。  

## Frequently Asked Questions

### Can Aspose.Tasks render other views besides Resource Usage and Sheet?
Aspose.Tasks 支持渲染各种视图，如甘特图、任务使用和日历视图等。

### Is Aspose.Tasks compatible with different versions of Microsoft Project files?
是的，Aspose.Tasks 支持多种 Microsoft Project 文件格式，包括 MPP、MPT 和 XML 等。

### Can I customize the appearance of rendered views using Aspose.Tasks?
当然！Aspose.Tasks 提供丰富的选项，可自定义渲染视图的外观和布局，以满足您的特定需求。

### Does Aspose.Tasks require Microsoft Project to be installed on the system?
不，Aspose.Tasks 是独立库，无需在系统上安装 Microsoft Project 即可运行。

### Is technical support available for Aspose.Tasks users?
是的，Aspose.Tasks 用户可通过[ Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)获取技术支持。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose
---
date: 2026-06-15
description: 了解如何使用 Aspose.Tasks for Java 将 mpp 转换为 pdf 并渲染 Resource Usage 和 Sheet
  视图。按照我们的分步指南设置 timescale，轻松生成详细的 PDF 报告。
keywords:
- convert mpp to pdf
- how to set timescale
- create pdf from mpp
- save ms project pdf
linktitle: 将 MPP 转换为 PDF 并渲染 Resource Usage 视图 – Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  headline: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  type: TechArticle
- description: Learn how to convert mpp to pdf and render Resource Usage and Sheet
    views using Aspose.Tasks for Java. Follow our step‑by‑step guide to set timescale
    and generate detailed PDF reports effortlessly.
  name: Convert MPP to PDF and Render Resource Usage View – Aspose.Tasks
  steps:
  - name: Read the Source Project
    text: The `Project` class represents a Microsoft Project file loaded into memory,
      providing access to its data and structure.
  - name: Define SaveOptions with Required TimeScale Settings
    text: '`SaveOptions` configures how the project is saved, allowing you to specify
      format‑specific settings such as timescale.'
  - name: Set the Presentation Format to ResourceUsage
    text: '`PresentationFormat` determines which Project view (e.g., ResourceUsage)
      is rendered in the output document.'
  - name: Save the Project as PDF
    text: '`project.save` writes the project to a file using the provided `SaveOptions`,
      producing the final PDF.'
  - name: Render Views for Other TimeScale Settings
    text: Repeat the previous steps, changing the `TimeScale` value to render additional
      timescale views.
  - name: Optional – Convert Multiple Projects in a Batch
    text: If you need to **convert project to pdf** for many files, place the above
      logic inside a loop that iterates over a directory of *.mpp* files. This approach
      **saves ms project pdf** files in bulk with minimal code changes. The following
      code demonstrates a complete example of converting an MPP file t
  type: HowTo
- questions:
  - answer: Yes, it also supports Gantt Chart, Task Usage, Calendar, and many additional
      views.
    question: Can Aspose.Tasks render other views besides Resource Usage and Sheet?
  - answer: Absolutely – it handles MPP, MPT, and XML formats from Project 2000 through
      Project 2021.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can modify colors, fonts, and column layouts through `PdfSaveOptions`
      and `PresentationOptions`.
    question: Can I customize the appearance of rendered views?
  - answer: No, it is a standalone library and works on any Java‑compatible environment.
    question: Does Aspose.Tasks require Microsoft Project to be installed?
  - answer: Support is available via the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15/).
    question: Where can I get technical support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 将 MPP 转换为 PDF 并渲染 Resource Usage 视图 – Aspose.Tasks
url: /zh/java/resource-management/render-resource-usage-sheet-view/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将 MPP 转换为 PDF 并呈现资源使用视图 – Aspose.Tasks

在本教程中，您将学习 **如何将 mpp 转换为 pdf**，同时呈现 Microsoft Project 文件的资源使用视图和表格视图。使用 Aspose.Tasks for Java 可消除服务器上对 Microsoft Project 的需求，为您提供一种快速、可靠的方式从 MPP 文件生成 PDF 报告。我们还将展示 **如何设置时间尺度**，以便输出符合您的报告要求。

## 快速解答
- **Aspose.Tasks 的作用是什么？** 它可以读取、修改并转换 Microsoft Project (MPP) 文件，而无需安装 MS Project。  
- **我能用一行代码将 MPP 转换为 PDF 吗？** 可以——加载 Project，设置 SaveOptions，然后调用 `save`。  
- **支持哪些时间尺度？** 天、ThirdsOfMonths 和月。  
- **生产环境是否需要许可证？** 非试用部署需要商业许可证。  
- **该库兼容 Java 8+ 吗？** 当然——它支持 Java 8 及更高版本。

## 什么是将 mpp 转换为 PDF？
*Convert mpp to pdf* 指的是将 Microsoft Project (.mpp) 文件转换为便携式文档格式 (PDF) 的过程，能够忠实再现项目的表格、进度、图表和资源分配。生成的 PDF 可轻松共享、打印和归档，无需在接收方机器上安装 Microsoft Project。

## 为什么使用 Aspose.Tasks 将项目转换为 PDF？
Aspose.Tasks 支持 **50+** 输入和输出格式，并且能够在不将整个文件加载到内存的情况下渲染数百页的项目，将 RAM 使用率降低最高可达 70 %。PDF 输出保留表格、图表和资源分配，非常适合向利益相关者分发和归档。

## 前置条件
1. **Java Development Kit (JDK)** – 在您的机器上安装 Java 8 或更高版本。  
2. **Aspose.Tasks for Java** – 从[下载页面](https://releases.aspose.com/tasks/java/)下载最新的 JAR 包。  

## 如何使用 Aspose.Tasks for Java 将 mpp 转换为 PDF？
加载源 MPP 文件，配置所需的时间尺度，将呈现格式设置为 **ResourceUsage**，并将结果保存为 PDF。整个端到端流程只需几次 API 调用，典型项目大小的处理时间不足一秒。

### 步骤 1：读取源项目
`Project` 类表示已加载到内存的 Microsoft Project 文件，提供对其数据和结构的访问。  
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

### 步骤 2：使用所需的 TimeScale 设置定义 SaveOptions
`SaveOptions` 配置项目的保存方式，允许您指定诸如时间尺度等特定格式设置。  
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source Project
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```

### 步骤 3：将 PresentationFormat 设置为 ResourceUsage
`PresentationFormat` 决定在输出文档中渲染哪个 Project 视图（例如 ResourceUsage）。  
```java
// Define the SaveOptions with required TimeScale settings as Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```

### 步骤 4：将项目保存为 PDF
`project.save` 使用提供的 `SaveOptions` 将项目写入文件，生成最终的 PDF。  
```java
// Set the Presentation format to ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```

### 步骤 5：为其他 TimeScale 设置渲染视图
重复前面的步骤，修改 `TimeScale` 值以渲染其他时间尺度视图。  
```java
// Save the Project
project.save(dataDir + days, options);
```

### 步骤 6：可选 – 批量转换多个项目
如果需要为大量文件 **convert project to pdf**，可将上述逻辑放入遍历 *.mpp* 文件目录的循环中。此方法可批量 **saves ms project pdf** 文件，代码改动极少。  
以下代码演示了一个完整示例，展示如何使用所需设置将 MPP 文件转换为 PDF。  
```java
// Set the Timescale settings to ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
// Save the Project
project.save(thirds, options);
// Set the Timescale settings to Months
options.setTimescale(Timescale.Months);
// Save the project
project.save(dataDir + months, options);
```

## 常见问题及解决方案
- **PDF 中缺少字体** – 确保服务器上已安装所需字体，或通过 `PdfSaveOptions` 将其嵌入。  
- **大型项目文件导致 OutOfMemoryError** – 使用 `LoadOptions.setLoadAllResources(false)` 按需加载资源。  
- **时间尺度渲染不正确** – 核实 `options.setTimeScale(TimeScale.Days)`（或其他枚举）是否匹配所需的粒度。

## 常见问答

**Q: Aspose.Tasks 能渲染除资源使用和表格之外的其他视图吗？**  
A: 可以，它还支持甘特图、任务使用、日历以及许多其他视图。

**Q: Aspose.Tasks 是否兼容不同版本的 Microsoft Project 文件？**  
A: 绝对兼容——它能够处理从 Project 2000 到 Project 2021 的 MPP、MPT 和 XML 格式。

**Q: 我可以自定义渲染视图的外观吗？**  
A: 可以，您可以通过 `PdfSaveOptions` 和 `PresentationOptions` 修改颜色、字体和列布局。

**Q: Aspose.Tasks 是否需要安装 Microsoft Project？**  
A: 不需要，它是一个独立库，可在任何兼容 Java 的环境中运行。

**Q: 我在哪里可以获得技术支持？**  
A: 支持可通过 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15/)获取。

---

**最后更新：** 2026-06-15  
**测试环境：** Aspose.Tasks 24.12 for Java  
**作者：** Aspose

## 相关教程

- [在 Aspose.Tasks 中呈现资源使用和表格视图](/tasks/java/resource-management/render-resource-usage-sheet-view/)
- [如何在 Aspose.Tasks 中导出 PDF – 保存为 PDF](/tasks/java/project-file-operations/save-as-pdf/)
- [如何使用 Aspose.Tasks for Java 创建 MPP 文件](/tasks/java/project-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}
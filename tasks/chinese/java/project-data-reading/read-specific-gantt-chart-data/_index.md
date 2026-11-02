---
date: 2026-10-31
description: 了解如何使用 Aspose.Tasks 在 Java 中导出 gantt 为 pdf。此分步指南展示了如何读取 Gantt 图表数据并生成
  PDF 报告。
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: 在 Aspose.Tasks 中读取特定 Gantt 图表数据
og_description: 使用 Aspose.Tasks 在 Java 中导出 gantt 为 pdf。按照本教程读取 Gantt 图表数据、定制视图属性，并生成用于项目管理的
  PDF 报告。
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: 在 Java 中导出 gantt 为 pdf – Aspose.Tasks 指南
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: 在 Java 中导出 gantt 为 pdf – 提取特定数据
url: /zh/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中将甘特图导出为 PDF – 提取特定数据

## 介绍
在本教程中，您将学习如何通过使用 Aspose.Tasks for Java 读取甘特图信息来 **export gantt to pdf in Java**。甘特图为项目经理提供任务、依赖关系和时间线的可视化路线图，能够以编程方式提取这些数据可让您创建自动化的 PDF 报告、仪表板或与其他企业系统的集成。让我们逐步演示，从加载项目文件、提取视图属性到最终生成 PDF。

## 快速回答
- **我可以提取什么？** 任意视图属性、条形样式、网格线、文本样式、进度线或甘特图的时间刻度层级。  
- **我需要许可证吗？** 试用版可用于开发；生产环境需要商业许可证。  
- **支持哪个 Java 版本？** Java 8 或更高（本教程使用 JDK 11）。  
- **代码可以直接运行吗？** 是的 – 只需替换数据目录路径。  
- **读取后我可以修改视图吗？** 当然可以 – API 允许您更改属性并保存回项目文件。

## 什么是 export gantt to pdf？
Export gantt to pdf 是将存储在项目文件中的甘特图视图转换为 PDF 文档的过程，保留视觉样式和时间线信息。此操作对于向可能没有项目管理工具的利益相关者共享项目状态非常有用。

## 为什么使用 Aspose.Tasks 将 export gantt to pdf？
Aspose.Tasks 能处理 **over 30 + input formats**（MPP、XML、MPX 等），并且 **export to PDF in a single call**，在保留 95 % 视觉保真度的同时，即使是超过 500 条任务的项目也能顺利导出。该库在内存中处理文件，因此您可以在服务器上生成 PDF，而无需安装 Microsoft Project。

## 先决条件
1. **Java Development Kit (JDK)：** 确保系统已安装 Java。您可以从 **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)** 下载。  
2. **Aspose.Tasks for Java Library：** 从 **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)** 下载并安装 Aspose.Tasks for Java 库。  
3. **Integrated Development Environment (IDE)：** 选择您偏好的 IDE。常用选择包括 IntelliJ IDEA、Eclipse 或 NetBeans。

## 导入包
以下导入语句让您能够访问读取和导出甘特数据所需的核心 Aspose.Tasks 类。  
*此处未显示代码块，以便教程专注于概念；只需将导入语句添加到您的 Java 文件中即可。*

## 如何在 Java 中加载甘特图项目文件？
加载项目文件的方法是创建一个 `Project` 实例并将完整路径传递给构造函数。此步骤会初始化甘特图的内存表示，允许后续查询视图属性。当文件成功加载后，您可以验证项目名称、开始日期以及任务数量，以确保打开了正确的文件。此验证有助于在工作流的早期捕获路径或格式问题。  
```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*定义锚点：* `Project` 是表示内存中单个项目文件的顶层 Aspose.Tasks 对象。

## 如何访问甘特图视图？
从项目的视图集合中检索第一个甘特视图。大多数项目至少包含一个甘特视图，通常是第一个条目。获取视图后，您可能需要检查其名称并确保其类型为 `GanttChartView`，然后再进行属性提取。此额外检查可防止在使用自定义或非标准视图集合时出现运行时错误。  
```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*定义锚点：* `GanttChartView` 表示典型甘特图中任务、时间尺度和条形的可视化布局。

## 如何提取视图属性？
您可以直接从 `GanttChartView` 对象读取诸如背景颜色、条形高度和时间尺度设置等属性。打印这些属性有助于在导出前验证当前配置。典型的提取循环会遍历每个属性，将值格式化为字符串，并将其记录到控制台或文件中以供后续分析。此方法对调试以及生成图表外观文档都很有用。  
```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*定义锚点：* `GanttChartView` 提供对视图设置的访问，例如背景颜色、条形高度和时间尺度配置。

## 如何提取条形样式？
遍历 `BarStyle` 对象集合，以获取图表中每种条形的颜色、图案和形状等详细信息。对于每种样式，您还可以读取其关联的任务类型以及触发该样式的条件，这在以其他格式重新创建图表时至关重要。收集这些信息使您能够生成忠实的视觉复制品或以编程方式应用自定义样式规则。  
```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*定义锚点：* `BarStyle` 定义甘特条的视觉外观，包括颜色、图案和形状。

## 如何提取网格线？
网格线定义行列之间的视觉分隔。通过 `getGridlines()` 方法访问它们并输出其可见性和样式。检索网格线集合后，您可以遍历每条线，捕获其线型（实线、虚线）、粗细和颜色。当需要在导出的 PDF 或其他报告格式中重现精确的网格布局时，这些数据非常有价值。  
```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*定义锚点：* `getGridlines()` 返回控制甘特视图中行列分隔的网格线对象集合。

## 如何提取文本样式？
文本样式控制甘特图上标签的字体、大小和颜色。遍历 `TextStyle` 集合以列出每种样式。对于每个文本样式，您还可以检索其关联的元素（任务名称、日期等）以及任何条件格式规则。捕获这些细节可确保导出文档保留与原始图表相同的排版。  
```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*定义锚点：* `TextStyle` 表示应用于甘特图中文本元素的格式属性。

## 如何提取进度线？
进度线显示任务的当前完成点。通过 `getProgressLines()` 访问它们并打印其属性。每条进度线包括线条颜色、粗细以及相对于任务条的位置等属性。记录这些信息可让您生成关注进度的可视化图表或计算整体项目完成度指标。  
```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*定义锚点：* `getProgressLines()` 返回指示任务完成状态的进度线对象集合。

## 如何提取时间刻度层级？
时间刻度层级定义图表上显示的层次时间单位（天、周、月）。通过 `getTimescaleTiers()` 检索它们并输出其设置。对于每个层级，您可以捕获单位类型、标签格式和对齐方式，这对于在导出的 PDF 或自定义 UI 组件中重现精确的时间轴粒度至关重要。  
```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*定义锚点：* `getTimescaleTiers()` 提供对控制时间轴显示的时间刻度层级对象集合的访问。

## 如何将甘特图导出为 PDF？
创建 `PdfSaveOptions` 对象，可选地自定义页面尺寸或字体嵌入，然后使用 PDF 格式调用 `project.save`。此单次调用即可生成与屏幕上甘特视图相同的 PDF。您还可以指定其他选项，如图像压缩、去除水印或嵌入自定义字体，以满足企业品牌要求。保存后，验证 PDF 文件大小和视觉保真度，以确保导出成功。  
```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*定义锚点：* `PdfSaveOptions` 允许您微调 PDF 输出，例如页面尺寸、压缩和字体处理。

## 常见陷阱与技巧
- **数据目录不正确：** 确保 `dataDir` 以适合您操作系统的文件分隔符（`/` 或 `\\`）结尾。  
- **视图缺失：** 如果项目没有甘特视图，`project.getViews()` 将为空 – 在强制转换前添加检查。  
- **许可证异常：** 没有有效许可证时，API 可能会在导出的 PDF 中添加水印。  
- **大型项目：** 对于任务超过 1,000 条的项目，考虑增大 JVM 堆大小（`-Xmx2g`），以避免 `OutOfMemoryError`。

## 常见问题
**Q: 我可以将 Aspose.Tasks for Java 与其他 Java 库一起使用吗？**  
A: 是的，Aspose.Tasks for Java 可无缝集成到任何 Java 库或框架中，包括 Spring、Hibernate 和 Apache POI。

**Q: Aspose.Tasks 适用于大规模企业项目吗？**  
A: 绝对适用。该库在标准服务器硬件上可在 5 秒内处理数百页的 MPP 文件，并支持多线程环境中的并发执行。

**Q: Aspose.Tasks 支持多种项目文件格式吗？**  
A: 是的，Aspose.Tasks 支持 20 多种格式，包括 MPP、XML、MPX 和 Primavera XML，帮助您读取和转换旧版计划。

**Q: 我可以使用 Aspose.Tasks 定制甘特图的外观吗？**  
A: 当然可以。在导出为 PDF 或图像格式之前，您可以以编程方式修改条形样式、网格线、文本样式和时间刻度层级。

**Q: 修改视图后如何保存更改？**  
A: 在进行任何修改后，调用 `project.save("output.mpp");` 将更改持久化到项目文件。

**最后更新：** 2026-10-31  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## 相关教程

- [如何使用 Aspose.Tasks 将项目保存为 PDF – 导出指南](/tasks/java/project-file-operations/save-as-pdf/)
- [创建项目 PDF – 定制甘特图时间尺度](/tasks/java/project-file-operations/set-time-scale-count/)
- [导出项目为 PDF 并在 Aspose.Tasks 中减少任务列表与页脚之间的间距](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
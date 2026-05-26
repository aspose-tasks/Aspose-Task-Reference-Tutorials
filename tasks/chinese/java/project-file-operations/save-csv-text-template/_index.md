---
date: 2026-05-26
description: 了解如何使用 Aspose.Tasks for Java 将 MPP 导出为 CSV、将项目保存为模板，以及将 MPP 转换为文本。
keywords:
- export mpp to csv
- save project as template
- convert mpp to csv
linktitle: 使用 Aspose.Tasks Java 将 MPP 导出为 CSV、文本和模板
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  headline: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to export MPP to CSV, save project as template, and convert
    MPP to text using Aspose.Tasks for Java.
  name: Export MPP to CSV, Text & Template with Aspose.Tasks Java
  steps:
  - name: Save as CSV
    text: '`SaveFileFormat.CSV` tells Aspose.Tasks to output the project in CSV format.'
  - name: Save as Text
    text: '`SaveFileFormat.TEXT` instructs the library to generate a plain‑text representation
      of the project.'
  - name: Set Template Options
    text: Use `Project.save` with `SaveFileFormat.MPT` (or `SaveFileFormat.TEMPLATE`)
      to create a template file that strips dates and baselines.
  type: HowTo
- questions:
  - answer: Yes, it fully supports tasks, resources, assignments, baselines, and custom
      fields across all Project versions up to 2024.
    question: Can Aspose.Tasks for Java handle complex, multi‑phase projects?
  - answer: Absolutely – download a free trial from [here](https://releases.aspose.com/).
    question: Is a trial version available?
  - answer: The official support forum is at [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      where staff and community members answer questions.
    question: Where can I get help if I run into problems?
  - answer: Yes, purchase a temporary license at [here](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for short‑term evaluation?
  - answer: It is fully cross‑platform and works on Windows, macOS, and Linux with
      any Java 8+ runtime.
    question: Does Aspose.Tasks run on Linux and macOS?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks Java 将 MPP 导出为 CSV、文本和模板
url: /zh/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 将 MPP 导出为 CSV、文本和模板

## 介绍
在本教程中，您将了解 **如何将 MPP 导出为 CSV**，创建可重用的项目模板，并使用 Aspose.Tasks for Java 库生成纯文本提取。无论您是构建报告管道、自动化项目创建，还是与其他系统集成，这些步骤都能帮助您从原始 MPP 文件快速得到所需的输出，而无需安装 Microsoft Project。

## 快速答案
- **我可以将 MPP 导出为 CSV 吗？** 是的 – 调用 `project.save("output.csv", SaveFileFormat.CSV)`。  
- **如何导出为纯文本？** 使用 `save` 方法并传入 `SaveFileFormat.TEXT`。  
- **“将项目另存为模板”有什么作用？** 它会创建一个 `.mpt` 文件，去除日期和基线，只保留骨架。  
- **我需要许可证吗？** 试用版可用于评估；商业许可证可移除评估限制。  
- **需要哪个 Java 版本？** 完全支持 Java 8 或更高版本。

## 什么是“将项目另存为模板”？
将项目另存为模板（`.mpt`）会捕获结构、任务层次和资源分配，同时去除实际的开始/结束日期和基线数据。这使得模板非常适合在多个新项目中重复使用标准项目布局。它保留所有自定义字段、成本费率和分配细节，确保模板可应用于任何新项目而不会丢失关键配置。

## 为什么使用 Aspose.Tasks for Java？
直接在 Java 中导出 MPP 为 CSV、文本或模板，无需 Microsoft Project。Aspose.Tasks 支持 **20 多个 Microsoft Project 版本**（2000‑2024），并且能够在内存高效模式下处理高达 **500 MB** 的文件，使其非常适合服务器端自动化、CI 管道和跨平台工具。

## 先决条件
- 已安装 Java Development Kit 8 或更高版本。  
- 已将 Aspose.Tasks for Java 库添加到项目中 – 从 [这里](https://releases.aspose.com/tasks/java/) 下载。  
- 您也可以在 [这里](https://releases.aspose.com/) 探索其他 Aspose 库。  
- 具备 Java 以及 Maven/Gradle 项目配置的基本知识。

## 导入包
`Project` 类是 Aspose.Tasks 的核心对象，表示内存中的 Microsoft Project 文件。将库添加到构建文件后，导入所需的类：

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## 将项目另存为 CSV（将 MPP 导出为 CSV）
将 MPP 文件导出为 CSV 可让您将任务数据导入 Excel、Power BI 或任何分析平台。

### 步骤 1：加载项目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步骤 2：另存为 CSV
`SaveFileFormat.CSV` 告诉 Aspose.Tasks 以 CSV 格式输出项目。  
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## 将项目另存为文本（如何导出文本）
纯文本文件提供任务、资源和分配的快速、人类可读的转储。

### 步骤 1：加载项目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步骤 2：另存为文本
`SaveFileFormat.TEXT` 指示库生成项目的纯文本表示。  
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## 将项目另存为模板（创建 Java 项目模板）

### 步骤 1：加载项目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步骤 2：设置模板选项
使用 `Project.save` 并传入 `SaveFileFormat.MPT`（或 `SaveFileFormat.TEMPLATE`）来创建一个去除日期和基线的模板文件。  
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```

### 步骤 3：另存为模板
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## 常见问题与技巧
- **文件未找到：** 验证 `YourProject.mpp` 的路径或使用绝对路径。  
- **许可证异常：** 没有有效许可证时，库以评估模式运行，可能会添加水印。请尽早应用许可证 (`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`)。  
- **大型项目：** 对于大于 200 MB 的文件，增加 JVM 堆内存 (`-Xmx2g`) 以防止 `OutOfMemoryError`。  
- **性能：** 在转换多个项目时，尽可能复用单个 `Project` 实例，以减少对象创建开销。

## 结论
我们已经演示了如何使用 Aspose.Tasks for Java **将 MPP 导出为 CSV**、**将 MPP 转换为文本**，以及 **将项目另存为模板**。这些功能使您能够自动化报告、创建标准化的项目骨架，并将项目数据集成到任何下游系统中——无需安装 Microsoft Project。

## 常见问题解答

**Q: Aspose.Tasks for Java 能处理复杂的多阶段项目吗？**  
A: 是的，它完全支持任务、资源、分配、基线和自定义字段，适用于所有截至 2024 年的 Project 版本。

**Q: 是否提供试用版？**  
A: 当然 – 从 [这里](https://releases.aspose.com/) 下载免费试用版。

**Q: 如果遇到问题，我可以在哪里获得帮助？**  
A: 官方支持论坛位于 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)，工作人员和社区成员会在此回答问题。

**Q: 我可以获取临时许可证进行短期评估吗？**  
A: 可以，在 [这里](https://purchase.aspose.com/temporary-license/) 购买临时许可证。

**Q: Aspose.Tasks 能在 Linux 和 macOS 上运行吗？**  
A: 它是完全跨平台的，可在 Windows、macOS 和 Linux 上运行，支持任何 Java 8+ 运行时。

---

**Last Updated:** 2026-05-26  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose

## 相关教程

- [如何创建 MPP 文件 – 使用 Aspose.Tasks 创建并保存空项目为 MPP 格式](/tasks/java/project-configuration/create-save-mpp/)
- [加载 MPP 文件 Java - 使用 Aspose.Tasks 管理项目属性](/tasks/java/project-management/default-properties/)
- [如何使用 Aspose.Tasks for Java 将 MPP 导出为 Excel](/tasks/java/project-file-operations/save-data-to-excel/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
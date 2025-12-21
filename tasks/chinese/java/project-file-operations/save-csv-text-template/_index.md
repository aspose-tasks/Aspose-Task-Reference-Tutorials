---
date: 2025-12-21
description: 了解如何使用 Aspose.Tasks for Java 将项目保存为模板、将 MPP 导出为 CSV，以及将 MPP 转换为文本。
linktitle: Save Project as Template, CSV, and Text with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 将项目保存为模板、CSV 和文本
url: /zh/java/project-file-operations/save-csv-text-template/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将项目另存为模板、CSV 和文本（使用 Aspose.Tasks）

## 介绍
在本教程中，您将了解 **如何将项目另存为模板**，以及如何使用 Aspose.Tasks for Java 将 Microsoft Project（MPP）文件导出为 CSV 和纯文本格式。无论是创建可重复使用的项目模板、生成用于分析的 CSV 报表，还是生成用于集成的简易文本提取，这些步骤都能帮助您快速高效地完成任务。

## 快速回答
- **可以将 MPP 导出为 CSV 吗？** 可以 – 使用 `project.save(..., SaveFileFormat.CSV)`。  
- **如何导出文本？** 使用 `SaveFileFormat.TEXT` 保存。  
- **“将项目另存为模板”有什么作用？** 它会生成一个 `.mpt` 文件，去除实际和基线值，便于重复使用。  
- **需要许可证吗？** 提供试用版；生产环境需要商业许可证。  
- **需要哪个 Java 版本？** 支持 Java 8 及以上。

## 什么是 “将项目另存为模板”？
将项目保存为模板（`.mpt`）会捕获结构、任务层级和资源分配，同时删除实际的开始/结束日期和基线数据。这使得模板非常适合在多个新项目中复用标准项目布局。

## 为什么选择 Aspose.Tasks for Java？
Aspose.Tasks 让您无需安装 Microsoft Project 即可操作 Microsoft Project 文件。它支持 **如何导出 MPP**、**如何导出文本**，以及 **将 MPP 转换为 CSV**，全部通过纯 Java 代码实现，非常适合服务器端自动化、CI 流水线或桌面工具。

## 前置条件
在开始之前，请确保您已具备：

1. 已安装 Java Development Kit (JDK) 8 或更高版本。  
2. 已将 Aspose.Tasks for Java 库添加到项目中。从 [此处](https://releases.aspose.com/tasks/java/) 下载。  
3. 具备基本的 Java 语法以及 Maven/Gradle 项目设置经验。

## 导入包
首先，在 Java 源文件中导入所需的类：

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

## 将项目另存为 CSV（导出 MPP 为 CSV）
将 MPP 文件导出为 CSV 对于在 Excel 或 BI 工具中进行数据分析非常有用。

### 步骤 1：加载项目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步骤 2：另存为 CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```

## 将项目另存为文本（导出文本）
如果需要任务、资源或分配的纯文本表示，请将项目保存为文本文件。

### 步骤 1：加载项目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步骤 2：另存为文本
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```

## 将项目另存为模板（创建项目模板 Java）
创建可重复使用的模板会去除实际日期和基线，只留下一个干净的骨架供新项目使用。

### 步骤 1：加载项目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```

### 步骤 2：设置模板选项
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
- **文件未找到：** 确认 `YourProject.mpp` 的路径是否正确，或使用绝对路径。  
- **许可证异常：** 若未使用有效许可证，库将在评估模式下运行并可能添加水印。请在代码中尽早应用许可证（`License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`）。  
- **大型项目：** 对于非常大的 MPP 文件，考虑增大 JVM 堆大小（`-Xmx2g`），以避免 `OutOfMemoryError`。

## 结论
我们已经介绍了 **如何将项目另存为模板**，以及 **如何将 MPP 导出为 CSV** 和 **转换为文本**，全部使用 Aspose.Tasks for Java。这些功能让您能够自动化项目数据处理、生成可重复使用的模板，并将项目信息集成到其他系统中，而无需安装 Microsoft Project。

## 常见问答
### 问：Aspose.Tasks for Java 能处理复杂的项目文件吗？
答：当然可以！Aspose.Tasks for Java 能轻松处理各种复杂程度的项目，全面支持 Microsoft Project 文件格式。  
### 问：是否提供 Aspose.Tasks for Java 的试用版？
答：是的，您可以从 [此处](https://releases.aspose.com/) 获取 Aspose.Tasks for Java 的免费试用。  
### 问：在哪里可以获得 Aspose.Tasks for Java 的支持？
答：您可以访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获取帮助或提出问题。  
### 问：我可以购买临时许可证吗？
答：可以，您可以在 [此处](https://purchase.aspose.com/temporary-license/) 购买临时许可证，以评估库的全部功能。  
### 问：Aspose.Tasks for Java 是否兼容不同操作系统？
答：是的，Aspose.Tasks for Java 兼容多种操作系统，包括 Windows、macOS 和 Linux。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}

---

**最近更新：** 2025-12-21  
**测试环境：** Aspose.Tasks for Java 24.12（最新）  
**作者：** Aspose  

---
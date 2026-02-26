---
date: 2026-02-26
description: 学习如何使用 Aspose.Tasks for Java 将项目保存为 PDF 并渲染任务表。通过本分步指南快速将 MPP 导出为 PDF。
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 将项目保存为 PDF – 使用 Aspose.Tasks for Java 渲染任务表
url: /zh/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 保存项目为 PDF – 在 Aspose.Tasks 中渲染任务表

## 介绍
在本综合指南中，您将学习如何 **save project as PDF** 并使用 Aspose.Tasks for Java 生成任务表。无论是需要将 MPP 文件导出为 PDF 供利益相关者审阅，还是仅仅渲染一份整洁的任务表用于报告，本教程都会逐步演示每一步，解释每个设置的意义，并提供您需要运行的完整代码。

## 快速答案
- **“save project as pdf” 是做什么的？** 它将 Microsoft Project 文件（MPP）转换为 PDF 文档，可选地将其格式化为任务表。  
- **任务表 PDF 使用哪种格式？** `PdfSaveOptions` 中的 `PresentationFormat.TaskSheet` 选项。  
- **运行代码是否需要许可证？** 生产环境需要临时或完整许可证；免费试用可用于评估。  
- **主要前置条件是什么？** Java JDK、Aspose.Tasks for Java 库，以及有效的项目文件（例如 *.mpp）。  
- **我可以自定义 PDF 布局吗？** 可以，Aspose.Tasks 提供了许多 `PdfSaveOptions` 属性用于样式和页面设置。

## 什么是 “save project as pdf”？
将项目保存为 PDF 会把内部项目数据转换为可移植的只读文档。这对于向没有安装 Microsoft Project 的利益相关者共享进度表、任务表或状态报告非常理想。

## 为什么要渲染任务表？
任务表以表格视图展示每个任务，显示 ID、名称、开始/结束日期以及其他字段。将其渲染为 PDF 可确保跨平台格式一致，且便于打印或嵌入其他文档。

## 前置条件
在开始之前，请确保您已经具备以下条件：

1. **Java Development Kit (JDK)** – 已安装最新版本，并且 `java`/`javac` 已加入 PATH。  
2. **Aspose.Tasks for Java** – 从官方站点[此处](https://releases.aspose.com/tasks/java/)下载库。  
3. 一个有效的 **project file**（`*.mpp`），例如 `NewProductDev.mpp`，用于转换。

## 导入包
首先，导入所需的 Aspose.Tasks 类。这些导入让您能够访问 PDF 保存选项、呈现格式以及核心的 `Project` 对象。

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## 步骤指南

### 步骤 1：设置文档目录
定义源 MPP 文件所在的文件夹以及生成的 PDF 将写入的目标文件夹。使用绝对路径或相对路径均可，只需确保该文件夹已存在。

```java
String dataDir = "Your Document Directory";
```

### 步骤 2：加载项目文件
通过加载现有的 MPP 文件创建 `Project` 实例。该对象在内存中表示整个项目结构。

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### 步骤 3：配置保存选项 – 将 MPP 导出为 PDF
实例化 `PdfSaveOptions` 并告知 Aspose.Tasks 您希望 PDF 以 **task sheet** 形式渲染。这是 *export project pdf* 用例的关键步骤。

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### 步骤 4：保存项目为任务表 – Save Project as PDF
在 `Project` 对象上调用 `save` 方法，传入目标文件名和已配置的选项。此操作 **将 MPP 文件转换为以任务表格式的 PDF**。

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### 步骤 5：检查结果
导航到您指定的目录（`dataDir`）。您应该能看到 `taskSheet.pdf`，其中包含整齐格式化的所有任务列表。使用任意 PDF 查看器打开，以验证转换是否成功。

## 常见问题及解决方案
- **FileNotFoundException** – 确保 `dataDir` 以路径分隔符（`/` 或 `\\`）结尾，并且 MPP 文件名正确。  
- **LicenseException** – 若出现许可证错误，请在调用任何 Aspose.Tasks API 之前应用临时或正式许可证。  
- **Blank PDF** – 验证项目中确实包含任务；空项目会生成空 PDF。

## 常见问答

**Q: Aspose.Tasks 是否兼容所有 Java 版本？**  
A: 是的，Aspose.Tasks 支持广泛的 Java 版本。详情请参阅[文档](https://reference.aspose.com/tasks/java/)。

**Q: 我可以在购买前试用 Aspose.Tasks 吗？**  
A: 当然！在[此处](https://releases.aspose.com/)探索免费试用版。

**Q: 我在哪里可以获得 Aspose.Tasks 的支持？**  
A: 加入 Aspose.Tasks 社区的[论坛](https://forum.aspose.com/c/tasks/15)获取支持和讨论。

**Q: 如何获取 Aspose.Tasks 的临时许可证？**  
A: 在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

**Q: 哪里可以购买 Aspose.Tasks for Java？**  
A: 在[此处](https://purchase.aspose.com/buy)购买 Aspose.Tasks for Java。

## 结论
通过遵循上述步骤，您已经学会了如何 **save project as PDF**，特别是使用 Aspose.Tasks for Java 渲染任务表。这一功能让您能够快速 *export MPP to PDF*，共享可读的项目快照，并将项目数据集成到更广泛的报告工作流中。

---

**最后更新：** 2026-02-26  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
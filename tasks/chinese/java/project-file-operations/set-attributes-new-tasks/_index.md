---
date: 2025-12-21
description: 学习如何使用 Aspose.Tasks for Java 创建项目并为新任务设置 MS Project 属性，包括如何将项目保存为 XML
  以及自定义任务属性。
linktitle: Set Attributes for New Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何创建项目 – 使用 Aspose.Tasks 设置新任务属性
url: /zh/java/project-file-operations/set-attributes-new-tasks/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何创建项目 – 使用 Aspose.Tasks 设置新任务属性

## 介绍
在本综合指南中，您将了解如何使用 Aspose.Tasks Java 库创建 **项目** 文件并为新任务设置 Microsoft Project 属性。我们将逐步演示，从准备开发环境到将项目保存为 XML 文件，帮助您轻松 **自定义任务属性** 并简化项目管理工作流。

## 快速答案
- **本教程涵盖什么内容？** 为新任务设置默认开始日期并将项目保存为 XML。  
- **需要哪个库？** Aspose.Tasks for Java。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证。  
- **我可以更改其他任务默认设置吗？** 可以，Aspose.Tasks 允许您修改许多任务级别的默认值。  
- **使用什么输出格式？** XML（SaveFileFormat.Xml）。

## Aspose.Tasks 中的项目是什么？
*项目* 是一个对象模型，映射 Microsoft Project 文件。它存储任务、资源、日历和其他调度数据，使您能够以编程方式读取、修改和生成项目文件。

## 为什么设置任务默认值？
为新任务设置默认值（如开始日期）可确保整个计划的一致性。它可以避免手动更新每个任务，降低调度错误的风险。

## 前提条件
1. **Java 开发环境** – 已安装 Java 8 或更高版本。  
2. **Aspose.Tasks for Java** – 从 [download link](https://releases.aspose.com/tasks/java/) 下载。  
3. **IDE** – Eclipse、IntelliJ IDEA 或任何兼容 Java 的编辑器。

## 导入包
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## 如何创建项目 – 设置新任务属性
### 步骤 1：定义数据目录
```java
String dataDir = "Your Data Directory";
```
将 `"Your Data Directory"` 替换为您希望保存输出文件的绝对路径。

### 步骤 2：创建 Project 实例
```java
Project prj = new Project();
```
这将创建一个空的项目，准备进行自定义。

### 步骤 3：设置新任务属性
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
上述代码行指示 Aspose.Tasks 将 **当前日期** 设为以后添加的任何任务的开始日期。

### 步骤 4：保存项目
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
这里我们 **将项目保存为 XML**，这是一种广泛支持的用于交换和后续处理的格式。

### 步骤 5：显示结果
```java
System.out.println("Project file generated Successfully");
```
简单的控制台消息确认文件已成功创建且没有错误。

## 如何设置任务属性
除了开始日期，您还可以使用 `Prj` 枚举修改其他默认任务设置，如持续时间、日历和优先级。这种灵活性使您能够 **自定义任务属性**，以符合组织的标准。

## 如何将项目保存为 XML
将项目保存为 XML 可保留完整的项目结构，同时保持文件可读性。它非常适合与其他工具、版本控制或自动化流水线集成。

## 常见问题及解决方案
- **无效的数据目录路径** – 确保文件夹存在且应用程序具有写入权限。  
- **未找到许可证** – 在创建 `Project` 对象之前加载 Aspose.Tasks 许可证，以避免评估水印。  
- **意外的开始日期** – 确认在设置后没有其他代码覆盖 `Prj.NEW_TASK_START_DATE`。

## 常见问答
### Q: 我可以使用 Aspose.Tasks for Java 来操作现有的项目文件吗？
A: 是的，Aspose.Tasks for Java 提供了丰富的功能来操作现有的项目文件，包括读取、修改以及以各种格式保存它们。

### Q: 我在哪里可以找到更多关于 Aspose.Tasks for Java 的文档和资源？
A: 您可以在 [Aspose.Tasks for Java 文档页面](https://reference.aspose.com/tasks/java/) 浏览文档和资源。

### Q: 是否有 Aspose.Tasks for Java 的免费试用版？
A: 是的，您可以从 [此处](https://releases.aspose.com/) 下载 Aspose.Tasks for Java 的免费试用版。

### Q: 我如何获取 Aspose.Tasks for Java 的临时许可证？
A: 可以在 [临时许可证页面](https://purchase.aspose.com/temporary-license/) 获取 Aspose.Tasks for Java 的临时许可证。

### Q: 我在哪里可以获得与 Aspose.Tasks for Java 相关的任何问题或查询的支持？
A: 您可以在 [Aspose.Tasks for Java 支持论坛](https://forum.aspose.com/c/tasks/15) 获取支持并与社区互动。

**Additional Q&A**

**Q: 创建项目后我可以更改默认开始日期吗？**  
A: 是的，您可以在添加新任务之前随时调用 `prj.set(Prj.NEW_TASK_START_DATE, ...)` 来更改。

**Q: 将项目保存为 XML 会影响大型项目的性能吗？**  
A: XML 基于文本，文件大小可能大于二进制格式，但对大多数常规项目规模仍保持较快的速度。

**Q: 还有其他可以全局设置的任务默认值吗？**  
A: 当然可以——诸如 `NEW_TASK_DURATION`、`NEW_TASK_COST` 和 `NEW_TASK_PRIORITY` 等属性也可以通过 `Prj` 枚举进行全局配置。

## 结论
您现在已经学习了使用 Aspose.Tasks for Java **创建项目** 文件、为新任务设置默认开始日期以及 **将项目保存为 XML**。通过掌握这些步骤，您可以轻松 **自定义任务属性**，以适应任何项目管理场景，提高一致性并节省宝贵时间。

---

**Last Updated:** 2025-12-21  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
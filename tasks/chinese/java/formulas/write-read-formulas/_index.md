---
date: 2025-12-07
description: 学习如何保存项目文件、编写和读取 MS Project 公式，以及使用 Aspose.Tasks for Java 添加自定义字段公式。
language: zh
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 保存项目文件并编写 MS Project 公式
url: /java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 保存项目文件并使用 Aspose.Tasks 编写 MS Project 公式

## Introduction
在项目管理领域，有效的数据处理至关重要。Aspose.Tasks for Java 是一个强大的解决方案，可帮助操作和提取 Microsoft Project 文件中的数据。它提供的一个强大功能是能够编写和读取 MS Project 公式。**您还将学习在应用这些公式后如何 *保存项目文件***，确保您的更改能够持久化，以便后续分析。本教程将指导您如何利用此功能提升项目管理工作。

## Quick Answers
- **“保存项目文件”做什么？** 它将所有内存中的更改写回磁盘上的 .mpp 文件。  
- **我可以添加自定义字段公式吗？** 可以——您可以创建自定义字段并分配诸如 “double task cost” 的公式。  
- **运行代码需要许可证吗？** 免费试用可用于评估；生产环境需要商业许可证。  
- **哪个 IDE 最合适？** 任意 Java IDE（IntelliJ IDEA、Eclipse、VS Code）都可以编译示例。  
- **API 是否兼容最新的 MS Project 版本？** Aspose.Tasks 支持所有近期的 .mpp 格式。

## What is “save project file” in Aspose.Tasks?
保存项目文件是指将 `Project` 对象的当前状态——包括任务、资源以及任何自定义公式——持久化到实际的 Microsoft Project 文件（`.mpp`）中。此操作在您修改数据后（例如添加自定义字段或更改任务成本）是必需的。

## Why add a custom field and create a custom field formula?
添加自定义字段为您提供了一个灵活的容器，用于存放默认字段未覆盖的额外信息。通过附加公式——例如 **double task cost**——您可以实现计算自动化，减少手动错误，并保持进度数据的一致性。

## Prerequisites
在开始本教程之前，请确保具备以下前置条件：

1. **Java Development Kit (JDK)** – 已在机器上安装 Java 8 或更高版本。  
2. **Aspose.Tasks for Java** – 从 [here](https://releases.aspose.com/tasks/java/) 下载并安装。  
3. **Integrated Development Environment (IDE)** – 选择您喜欢的 Java 开发 IDE（IntelliJ IDEA、Eclipse、VS Code 等）。

## Importing Packages
要开始，请在 Java 项目中导入必要的包：

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## Step 1: Set Up Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
定义存放 MS Project 文件的文件夹。这是您加载源文件并随后 **保存项目文件** 的位置。

## Step 2: Load Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
将现有的 Microsoft Project 文件加载到 `Project` 对象中，以便读取或修改其内容。

## Step 3: Add Custom Field and Create Custom Field Formula
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
在此步骤中，我们 **添加自定义字段** “Double Costs” 并 **创建自定义字段公式**，该公式将任务的 `[Cost]` 乘以 2，从而实现 **double task cost**。`setFormula` 方法直接将计算嵌入项目文件。

## Step 4: Add Task and Set Cost
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
创建一个新任务，然后将基础成本设为 `100`。保存项目时，自定义字段会自动显示 `200`，因为之前定义的公式。

## Step 5: Save Project File
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
最后，使用 **保存项目文件** 将所有修改写入。`save` 方法将更新后的项目（包括新自定义字段及其计算值）写入 `saved.mpp`。

## Common Issues and Solutions
| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **公式未应用** | 自定义字段未添加到项目的 `ExtendedAttributes` 集合中。 | 确保在保存之前执行 `project.getExtendedAttributes().add(attr);`。 |
| **文件未找到** | `dataDir` 路径不正确。 | 确认目录字符串以路径分隔符结尾（`/` 或 `\\`）。 |
| **成本显示为 0** | 任务成本在保存前未设置。 | 在 `project.save` 之前调用 `task.set(Tsk.COST, ...)`。 |

## Frequently Asked Questions
**Q: Aspose.Tasks 是否兼容所有版本的 MS Project？**  
A: 是的，Aspose.Tasks 支持广泛的 MS Project 版本，从较旧的 .mpp 格式到最新发布的版本。

**Q: 我可以将 Aspose.Tasks 集成到现有的 Java 项目中吗？**  
A: 当然可以。该 API 设计为无缝集成；只需将 Aspose.Tasks JAR 添加到项目的类路径即可。

**Q: 创建公式有什么限制吗？**  
A: 该库支持大多数原生 MS Project 公式语法，包括算术、逻辑和内置函数。复杂的自定义函数可能需要变通方案。

**Q: Aspose.Tasks 是否支持多平台部署？**  
A: 是的，该库可在任何支持 Java 的平台上运行，包括 Windows、Linux 和 macOS。

**Q: 如何获取 Aspose.Tasks 的技术支持？**  
A: 访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 获取社区帮助，或在拥有商业许可证时提交支持工单。

## Conclusion
在本教程中，我们介绍了如何使用 Aspose.Tasks for Java **保存项目文件**、**添加自定义字段**，以及 **创建自定义字段公式**，实现 **double task cost**。通过遵循这些步骤，您可以实现计算自动化，丰富项目数据，并确保所有更改持久化，以便后续报告和分析。

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
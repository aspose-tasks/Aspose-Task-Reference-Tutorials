---
date: 2026-02-13
description: 了解如何在 Aspose.Tasks Java 中创建新活动、设置数据目录并将项目保存为 MPP。本分步指南还涵盖了自定义表字段。
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何创建新活动并设置 Aspose.Tasks 数据目录
url: /zh/java/project-configuration/configure-gantt-chart/
weight: 10
---

 as is.

Let's craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中创建新活动并设置数据目录

## 介绍
在本教程中，您将学习**如何设置数据目录**、**如何创建新活动**，以及在使用 Java 的 Aspose.Tasks 项目中配置甘特 MS Project 图表视图时**将项目保存为 MPP**。Aspose.Tasks 是一个强大的 Java API，能够以编程方式操作 Microsoft Project 文件。阅读完本指南后，您将能够**自定义表字段**、调整数据目录，并以您需要的方式可视化项目。

## 快速答案
- **第一步是什么？** 设置项目文件所在的数据目录路径。  
- **需要哪个库？** Aspose.Tasks for Java（可从官方网站下载）。  
- **可以添加自定义属性吗？** 可以——您可以定义扩展属性并在甘特图中显示它们。  
- **测试时需要许可证吗？** 有临时许可证可用于评估。  
- **哪个 IDE 最适合？** 任意 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）均可。

## 什么是“设置数据目录”，它为何重要？
设置数据目录告诉 Aspose.Tasks 在何处读取和写入项目文件。如果路径不正确，API 将找不到您的 `.mpp` 文件，导致 FileNotFound 错误。在代码开头定义此目录，可使后续工作流保持整洁且可重复。

## 为什么要在甘特图中自定义表字段？
自定义表字段可以直接在甘特视图中展示额外信息——例如自定义属性、资源数据或项目特定备注。这使得图表对相关方更具信息价值，减少在多个报告之间切换的需求。

## 如何创建新活动？
创建新活动（任务）是构建或更新项目进度表的核心操作之一。通过编程方式添加任务，您可以自动生成复杂的项目计划、集成其他系统的数据，或在不手动编辑的情况下批量修改。

## 前置条件
在开始之前，请确保您已具备：

1. **Java Development Kit (JDK)** – 任意近期版本（8 以上）。  
2. **Aspose.Tasks 库** – 从[此处](https://releases.aspose.com/tasks/java/)下载。  
3. **IDE** – IntelliJ IDEA、Eclipse 或您偏好的任何 Java 兼容编辑器。

## 导入包
首先，导入 Aspose.Tasks 命名空间，以便使用其类：

```java
import com.aspose.tasks.*;
```

## 步骤指南

### 步骤 1：设置数据目录
定义包含项目文件的文件夹。这就是本教程重点的**设置数据目录**步骤。

```java
String dataDir = "Your Data Directory";
```

将 `"Your Data Directory"` 替换为存放 `project.mpp` 的文件夹的绝对路径。

### 步骤 2：加载项目文件
通过加载现有的 Microsoft Project 文件来创建 `Project` 实例。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 步骤 3：添加新活动
在项目根节点插入一个新任务（活动），演示**如何以编程方式创建新活动**。

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### 步骤 4：定义自定义属性
创建一个自定义属性定义，以便后续附加到任务上。

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### 步骤 5：将自定义属性添加到任务
将新定义的属性分配给您创建的任务。

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### 步骤 6：自定义表 – **customize table fields**
将自定义属性作为列添加到甘特图表中，指定宽度、标题和对齐方式。

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### 步骤 7：保存项目
将更改持久化到一个新文件，以便在 Microsoft Project 中打开。此步骤**将项目保存为 MPP**。

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## 常见问题及解决方案
| 问题 | 出现原因 | 解决方案 |
|------|----------|----------|
| **FileNotFoundException** 在加载项目时 | **设置数据目录** 路径不正确或缺少结尾的斜杠。 | 确认 `dataDir` 指向准确的文件夹，并包含正确的文件分隔符（`/` 或 `\\`）。 |
| 自定义属性在甘特视图中不可见 | 表字段添加到了错误的索引，或列宽过小。 | 确保 `table.getTableFields().add(3, attrField);` 使用了有效索引，并根据需要调整 `setWidth`。 |
| 保存时出现 LicenseException | 未为生产环境应用有效许可证。 | 在调用 `project.save()` 前应用临时或永久许可证。 |

## 常见问答

**问：我可以在其他编程语言中使用 Aspose.Tasks 吗？**  
答：可以，Aspose.Tasks 支持多种编程语言，包括 .NET、Java 和 C++。

**问：Aspose.Tasks 有免费试用吗？**  
答：有，您可以从[此处](https://releases.aspose.com/)下载免费试用版。

**问：在哪里可以获得 Aspose.Tasks 的支持？**  
答：您可以在 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 提问并获取帮助。

**问：如何购买 Aspose.Tasks 的许可证？**  
答：请前往[此处](https://purchase.aspose.com/buy)进行购买。

**问：测试时需要临时许可证吗？**  
答：是的，您可以从[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

## 结论
您已经学习了如何**设置数据目录**、**创建新活动**、定义并附加自定义属性，以及在使用 Aspose.Tasks for Java 时**将项目保存为 MPP**并**自定义表字段**。这些步骤让您能够完全控制项目数据的展示，使甘特图更具信息性并符合相关方的需求。

---

**最后更新：** 2026-02-13  
**测试环境：** Aspose.Tasks Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
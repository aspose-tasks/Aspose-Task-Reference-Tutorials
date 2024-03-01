---
title: 在 Aspose.Tasks 中编写和读取 MS 项目公式
linktitle: 在 Aspose.Tasks 中写入和读取公式
second_title: Aspose.Tasks Java API
description: 学习使用 Aspose.Tasks for Java 高效地编写和读取 MS Project 公式。提高您的项目管理技能。
type: docs
weight: 12
url: /zh/java/formulas/write-read-formulas/
---
## 介绍
在项目管理领域，有效处理数据至关重要。 Aspose.Tasks for Java 是一个强大的解决方案，有助于从 Microsoft Project 文件中操作和提取数据。它提供的一项强大功能是能够编写和读取 MS Project 公式。本教程将指导您完成利用此功能来增强项目管理任务的过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 Java。
2.  Aspose.Tasks for Java：从以下位置下载并安装 Aspose.Tasks for Java：[这里](https://releases.aspose.com/tasks/java/).
3. 集成开发环境 (IDE)：选择您首选的 IDE 进行 Java 开发。

## 导入包
首先，将必要的包导入您的 Java 项目：
```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## 第1步：设置数据目录
```java
//文档目录的路径。
String dataDir = "Your Data Directory";
```
在此步骤中，定义 MS Project 文件所在的目录。
## 第2步：加载项目文件
```java
Project project = new Project(dataDir + "project.mpp");
```
在这里，将 MS Project 文件加载到`Project`用于操纵的对象。
## 第 3 步：定义自定义公式
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");
project.getExtendedAttributes().add(attr);
```
此步骤涉及使用使任务成本加倍的公式创建自定义字段。
## 步骤 4：添加任务并设置成本
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
这里添加了一个新任务，并将其成本设置为 100。
## 第5步：保存项目文件
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
最后保存修改后的工程文件。

## 结论
在本教程中，我们探索了如何使用 Aspose.Tasks for Java 编写和读取 MS Project 公式。通过执行这些步骤，您可以有效地操作项目数据以满足您的特定要求。
## 常见问题解答
### Aspose.Tasks 与所有版本的 MS Project 兼容吗？
Aspose.Tasks 提供与各种版本的 MS Project 的兼容性，确保用户的灵活性。
### 我可以将 Aspose.Tasks 集成到我现有的 Java 项目中吗？
绝对地！ Aspose.Tasks 通过简单的 API 使用提供与 Java 项目的无缝集成。
### 我可以创建的公式类型有任何限制吗？
借助 Aspose.Tasks，您可以非常灵活地根据您的项目需求创建自定义公式。
### Aspose.Tasks支持多平台部署吗？
是的，Aspose.Tasks 支持跨多个平台部署，增强了其多功能性。
### 我如何获得 Aspose.Tasks 的技术支持？
如需技术援助和社区支持，请访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).
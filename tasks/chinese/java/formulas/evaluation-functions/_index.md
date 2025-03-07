---
title: 支持 Aspose.Tasks 公式中的评估函数
linktitle: 支持 Aspose.Tasks 公式中的评估函数
second_title: Aspose.Tasks Java API
description: 了解如何使用 Java 支持对 Aspose.Tasks 公式中的 MS Project 函数求值。使用 Aspose.Tasks 提高您的工作效率。
weight: 10
url: /zh/java/formulas/evaluation-functions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 支持 Aspose.Tasks 公式中的评估函数


## 介绍
Aspose.Tasks for Java 是一个功能强大的库，使开发人员能够以编程方式操作 Microsoft Project 文件。其主要功能之一是能够支持在 Aspose.Tasks 公式中评估 MS Project 函数。此功能允许用户直接在其 Java 应用程序中执行复杂的计算和分析。
## 先决条件
在开始将 MS Project 函数集成到 Aspose.Tasks 公式之前，请确保您具备以下条件：
1. Java 开发环境：确保您的系统上安装了 Java 以及用于 Java 开发的兼容 IDE，例如 IntelliJ IDEA 或 Eclipse。
2.  Aspose.Tasks for Java 库：下载 Aspose.Tasks for Java 库并将其包含在您的 Java 项目中。您可以从[Aspose.Tasks for Java 下载页面](https://releases.aspose.com/tasks/java/).
## 导入包
首先，在 Java 类中导入必要的包以利用 Aspose.Tasks 功能：
```java
import com.aspose.tasks.*;
```

## 第 1 步：创建一个新的项目对象
首先，创建一个新的`Project`使用对象：
```java
Project project = new Project();
```
这会初始化一个新的空项目。
## 步骤 2：定义任务的扩展属性
接下来，定义任务的扩展属性。该属性将保存与任务关联的自定义数据：
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
在这里，我们创建一个类型的扩展属性`Number`任务名称为“Sine”。
## 第3步：将扩展属性添加到项目中
将扩展属性定义添加到项目的扩展属性列表中：
```java
project.getExtendedAttributes().add(attr);
```
这会将自定义属性添加到项目中。
## 第 4 步：创建新任务
现在，让我们在项目中创建一个新任务：
```java
Task task = project.getRootTask().getChildren().add("Task");
```
这将向项目添加一个名为“Task”的新任务。
## 步骤 5：将扩展属性与任务关联
将之前创建的扩展属性与任务相关联：
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
这会将“Sine”扩展属性与任务关联起来。

## 结论
总之，将 MS Project 函数集成到 Java 中的 Aspose.Tasks 公式中是一个简单的过程。通过遵循提供的步骤，您可以有效地利用 Aspose.Tasks for Java 的强大功能以编程方式操作和分析 Microsoft Project 文件。
## 常见问题解答
### 问：Aspose.Tasks for Java 可以处理复杂的 MS Project 公式吗？
答：是的，Aspose.Tasks for Java 支持评估各种 MS Project 函数，允许在 Java 应用程序中进行复杂的计算。
### 问：Aspose.Tasks for Java 是否与不同版本的 Microsoft Project 文件兼容？
答：是的，Aspose.Tasks for Java 支持各种版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。
### 问：我可以在购买前试用 Aspose.Tasks for Java 吗？
答：是的，您可以从网站下载 Aspose.Tasks for Java 的免费试用版[这里](https://purchase.aspose.com/buy).
### 问：如何获得 Aspose.Tasks for Java 的支持？
答：您可以从 Aspose.Tasks 社区论坛获得支持[这里](https://forum.aspose.com/c/tasks/15).
### 问：Aspose.Tasks for Java 是否有可用的临时许可证？
答：是的，您可以从 Aspose 网站获取用于测试目的的临时许可证[这里](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

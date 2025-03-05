---
title: 在 Aspose.Tasks 中另存为 CSV、文本和模板
linktitle: 在 Aspose.Tasks 中另存为 CSV、文本和模板
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 将 Microsoft Project 文件保存为 CSV、文本和模板格式。
type: docs
weight: 16
url: /zh/java/project-file-operations/save-csv-text-template/
---
## 介绍
在本教程中，我们将探索如何使用 Aspose.Tasks for Java 以各种格式（例如 CSV、文本和模板）保存项目文件。 Aspose.Tasks 是一个功能强大的 Java 库，允许开发人员使用 Microsoft Project 文件，而无需安装 Microsoft Project。
## 先决条件
在我们开始之前，请确保您具备以下先决条件：
1. 您的系统上安装了 Java 开发工具包 (JDK)。
2.  Aspose.Tasks for Java 库已下载并在您的 Java 项目中配置。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/java/).
3. Java 编程语言的基础知识。

## 导入包
首先，您需要在 Java 文件中导入必要的包：
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## 将项目另存为 CSV
让我们分解一下将项目另存为 CSV 的步骤：
### 第 1 步：加载项目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 第 2 步：另存为 CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## 将项目另存为文本
以下是将项目另存为文本的方法：
### 第 1 步：加载项目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 第 2 步：另存为文本
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## 将项目另存为模板
将项目保存为模板涉及以下步骤：
### 第 1 步：加载项目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 第 2 步：设置模板选项
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### 第 3 步：另存为模板
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for Java 将 Microsoft Project 文件另存为 CSV、文本和模板。通过这些简单的步骤，您可以有效地管理各种格式的项目文件，从而提高 Java 开发人员的工作效率。
## 常见问题解答
### 问：Aspose.Tasks for Java 可以处理复杂的项目文件吗？
答：当然！ Aspose.Tasks for Java 可以轻松处理不同复杂程度的项目，为 Microsoft Project 文件格式提供全面支持。
### 问：Aspose.Tasks for Java 有试用版吗？
答：是的，您可以从以下位置获得 Aspose.Tasks for Java 的免费试用版：[这里](https://releases.aspose.com/).
### 问：在哪里可以找到 Aspose.Tasks for Java 的支持？
答：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)有关 Aspose.Tasks for Java 的任何帮助或疑问。
### 问：我可以购买 Aspose.Tasks for Java 的临时许可证吗？
答：是的，您可以从以下位置购买临时许可证：[这里](https://purchase.aspose.com/temporary-license/)，让您能够评估图书馆的全部潜力。
### 问：Aspose.Tasks for Java 是否兼容不同的操作系统？
答：是的，Aspose.Tasks for Java 与各种操作系统兼容，包括 Windows、macOS 和 Linux。
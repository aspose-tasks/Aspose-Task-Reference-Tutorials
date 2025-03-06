---
title: 使用 Aspose.Tasks 确定 MS Project 版本
linktitle: 使用 Aspose.Tasks 确定项目版本
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 以编程方式确定 MS Project 文件的版本。带有代码示例的分步指南。
type: docs
weight: 12
url: /zh/java/project-management/determine-version/
---
## 介绍
本教程将指导您使用 Aspose.Tasks for Java 逐步确定 MS Project 文件的版本。 Aspose.Tasks 是一个功能强大的 Java API，允许开发人员操作 Microsoft Project 文件，而无需安装 Microsoft Project。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 JDK。
2.  Aspose.Tasks for Java JAR 文件：从以下位置下载 Aspose.Tasks for Java 库[网站](https://releases.aspose.com/tasks/java/)并将其添加到您的 Java 项目中。
3. MS Project 文件：准备 MS Project 文件（XML 格式）用于测试。

## 导入包
在深入研究代码之前，让我们导入必要的包：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## 第 1 步：设置项目
```java
//文档目录的路径。
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`包含 MS Project 文件的目录路径。
## 第 2 步：加载项目
```java
Project project = new Project(dataDir + "input.xml");
```
代替`"input.xml"`与您的 MS Project 文件的名称。
## 第3步：确定项目版本
```java
//显示项目版本属性
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
此代码片段检索并打印 MS Project 文件的版本和上次保存日期。
## 第四步：显示结果
```java
//显示转换结果。
System.out.println("Process completed Successfully");
```
该行表示该过程已完成。

## 结论
在本教程中，您学习了如何使用 Aspose.Tasks for Java 确定 MS Project 文件的版本。通过遵循分步指南，您可以轻松地在 Java 应用程序中高效地使用 MS Project 文件。

## 常见问题解答
### 问：我可以将 Aspose.Tasks 与其他编程语言一起使用吗？
答：是的，Aspose.Tasks 支持多种编程语言，包括.NET、Java 和 C++.
### 问：Aspose.Tasks 适合大型项目吗？
答：当然，Aspose.Tasks 旨在轻松处理任何规模的项目。
### 问：我可以使用 Aspose.Tasks 自定义项目数据吗？
答：是的，您可以使用 Aspose.Tasks 操作项目数据、修改任务、资源等等。
### 问：Aspose.Tasks 是否需要安装 Microsoft Project？
答：不需要，Aspose.Tasks 独立工作，不需要安装 Microsoft Project。
### 问：Aspose.Tasks 是否提供技术支持？
答：是的，您可以从 Aspose.Tasks 论坛获得技术支持：[这里](https://forum.aspose.com/c/tasks/15).
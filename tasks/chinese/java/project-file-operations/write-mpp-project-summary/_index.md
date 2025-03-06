---
title: 在Aspose.Tasks中编写MPP项目摘要
linktitle: 在Aspose.Tasks中编写MPP项目摘要
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks 在 Java 中编写 MPP 项目摘要。轻松设置和检索项目信息。
weight: 27
url: /zh/java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在Aspose.Tasks中编写MPP项目摘要

## 介绍
在本教程中，我们将学习如何利用 Aspose.Tasks for Java 编写 MPP 项目摘要。 Aspose.Tasks 是一个功能强大的 Java 库，用于处理 Microsoft Project 文件。通过执行下面概述的步骤，您将能够使用此库设置和检索有关项目的各种摘要信息。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 JDK。
2.  Aspose.Tasks for Java：下载并安装 Aspose.Tasks for Java 库。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/java/).
3. 集成开发环境 (IDE)：选择用于 Java 开发的首选 IDE，例如 IntelliJ IDEA、Eclipse 或 NetBeans。

## 导入包
首先，将必要的包导入到您的 Java 类中：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## 第 1 步：设置项目并定义摘要信息
```java
//文档目录的路径。
String dataDir = "Your Data Directory";
//使用项目文件的路径初始化新的 Project 对象
Project project = new Project(dataDir + "project.mpp");
//设置有关项目的摘要信息
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
//设置项目的创建日期
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
//为项目设置关键词
project.set(Prj.KEYWORDS, "MPP Aspose");
//设置项目的最后打印日期
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## 第 2 步：保存项目摘要信息
```java
//以 MPP 格式保存项目
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
//显示成功消息
System.out.println("Process completed Successfully");
```
## 第 3 步：阅读项目摘要信息
```java
//阅读项目摘要信息
project = new Project(dataDir + "MppAspose.xml");
//项目的打印作者
System.out.println("Author: " + project.get(Prj.AUTHOR));
//打印项目的最后一位作者
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
//打印项目的修订号
System.out.println("Revision: " + project.get(Prj.REVISION));
//打印项目的关键字
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
//打印项目的评论
System.out.println("Comments: " + project.get(Prj.COMMENTS));
//打印项目的创建日期
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
//打印项目的关键字（再次）
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
//打印项目的最后打印日期
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## 结论
在本教程中，我们介绍了如何使用 Aspose.Tasks for Java 编写 MPP 项目摘要。通过执行这些步骤，您可以有效地设置和检索有关项目文件的各种摘要信息。 Aspose.Tasks 简化了在 Java 应用程序中使用 Microsoft Project 文件的过程，提供了强大的功能和易用性。
## 常见问题解答
### 问：我可以将 Aspose.Tasks for Java 与其他 Java 库一起使用吗？
答：是的，Aspose.Tasks for Java 可以与其他 Java 库无缝集成，以增强您的项目管理能力。
### 问：Aspose.Tasks for Java 有试用版吗？
答：是的，您可以从以下位置下载免费试用版：[这里](https://releases.aspose.com/).
### 问：Aspose.Tasks for Java 的更新频率是多少？
答：Aspose.Tasks for Java 会定期更新，以确保与最新版本的 Java 和 Microsoft Project 文件兼容。
### 问：我可以进一步自定义项目摘要信息吗？
答：当然，Aspose.Tasks for Java 提供了广泛的选项，可根据您的具体要求自定义项目摘要信息。
### 问：在哪里可以获得 Aspose.Tasks for Java 的支持？
答：您可以从 Aspose.Tasks 社区论坛获得支持[这里](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

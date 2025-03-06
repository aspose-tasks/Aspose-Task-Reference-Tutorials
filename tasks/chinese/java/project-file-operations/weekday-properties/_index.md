---
title: Aspose.Tasks 中的工作日属性
linktitle: Aspose.Tasks 中的工作日属性
second_title: Aspose.Tasks Java API
description: 了解在 Aspose.Tasks for Java 中有效管理工作日属性。轻松自定义周开始日期、每月天数等。
weight: 25
url: /zh/java/project-file-operations/weekday-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的工作日属性

## 介绍
Aspose.Tasks for Java 是一个功能强大的 API，使 Java 开发人员无需在计算机上安装 Microsoft Project 即可使用 Microsoft Project 文件。其关键功能之一是管理工作日属性，允许用户自定义周开始日期、每月天数、每天分钟数和每周分钟数。本教程将提供有关如何有效利用这些功能的详细指南。
## 先决条件
在深入研究 Aspose.Tasks for Java 之前，请确保您具备以下先决条件：
### Java 开发工具包 (JDK)
确保您的系统上安装了 JDK。您可以从 Oracle 网站下载并安装最新的 JDK。
### Java 库的 Aspose.Tasks
从网站下载并安装 Aspose.Tasks for Java 库。您可以访问下载链接[这里](https://releases.aspose.com/tasks/java/).
### 集成开发环境（IDE）
选择您喜欢的 Java 开发 IDE。流行的选择包括 IntelliJ IDEA、Eclipse 或 NetBeans。
## 导入包
首先，将必要的 Aspose.Tasks 包导入到您的 Java 项目中。就是这样：

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

现在，让我们将提供的示例分解为多个步骤，以便更好地理解。
## 第 1 步：加载项目文件
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
此步骤涉及从指定的数据目录加载名为“project.mpp”的项目文件。
## 第 2 步：显示工作日属性
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
在这里，我们检索并打印加载项目的周开始日期、每月天数、每天分钟数和每周分钟数属性。
## 步骤 3：设置工作日属性
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
此步骤涉及创建新的项目实例并设置自定义工作日属性，例如一周开始日、每月天数、每天分钟数和每周分钟数。
## 第 4 步：保存项目
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
最后，我们将修改后的项目与更新的工作日属性保存为 XML 文件。
## 第5步：显示结果
```java
System.out.println("Process completed Successfully");
```
此步骤确认该过程已成功完成。
## 结论
掌握 Aspose.Tasks for Java 中的工作日属性对于有效的项目管理至关重要。通过学习本教程，您已经学会了如何轻松操作和自定义工作日属性。探索更多文档和示例以增强您的项目管理能力。
## 常见问题解答
### 问：Aspose.Tasks for Java 可以处理复杂的项目结构吗？
答：是的，Aspose.Tasks for Java 为轻松处理复杂的项目结构提供了全面的支持。
### 问：Aspose.Tasks for Java 是否与不同版本的 Microsoft Project 文件兼容？
答：当然，Aspose.Tasks for Java 支持各种版本的 Microsoft Project 文件，确保跨平台的兼容性。
### 问：我可以将 Aspose.Tasks for Java 集成到我现有的 Java 应用程序中吗？
答：是的，Aspose.Tasks for Java 提供无缝集成功能，允许您通过强大的项目管理功能增强 Java 应用程序。
### 问：Aspose.Tasks for Java 是否提供文档和支持？
答：是的，您可以在其网站上访问 Aspose.Tasks for Java 的广泛文档和社区支持。[网站](https://releases.aspose.com/).
### 问：Aspose.Tasks for Java 是否有免费试用版？
答：是的，您可以从他们的网站下载 Aspose.Tasks for Java 的免费试用版[网站](https://reference.aspose.com/tasks/java/)在购买之前探索其功能。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

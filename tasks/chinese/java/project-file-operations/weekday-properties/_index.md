---
date: 2025-12-23
description: 学习如何使用 Aspose.Tasks Java 更新项目计划，设置一周的起始日，更改每月天数，并高效地自定义项目日历。
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java – 管理工作日属性
url: /zh/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java – 管理工作日属性

## 介绍
Aspose.Tasks for Java（aspose tasks java）是一套强大的 API，允许 Java 开发者在不安装 Microsoft Project 的情况下处理 Microsoft Project 文件。在本教程中，你将学习如何 **加载 MPP 文件**、**设置一周的起始日**、**更改每月天数**，以及 **自定义项目日历**——这些都是更新项目进度表的关键步骤。完成后，你将能够以编程方式调整工作日属性，并以所需格式保存更改。

## 快速答案
- **处理项目的主要类是什么？** `Project` 来自 Aspose.Tasks 库。  
- **如何更改一周的起始日？** 使用 `project.set(Prj.WEEK_START_DAY, DayType.Monday)`。  
- **我可以加载已有的 .mpp 文件吗？** 可以——使用文件路径实例化 `Project`。  
- **哪个方法可以将项目保存为 XML？** `project.save(path, SaveFileFormat.Xml)`。  
- **开发时需要许可证吗？** 免费试用可用于评估；生产环境需要许可证。

## 前置条件
在开始之前，请确保具备以下条件：

- **Java Development Kit (JDK)** – 已安装最新版本。  
- **Aspose.Tasks for Java 库** – 在此处下载 [here](https://releases.aspose.com/tasks/java/)。  
- **IDE**，如 IntelliJ IDEA、Eclipse 或 NetBeans。  

## 导入包
首先，导入必要的 Aspose.Tasks 类：

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

现在让我们逐步演示如何管理工作日属性。

## 步骤 1：加载 MPP 文件
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
*此处我们 **加载已有的 .mpp 文件**（`load mpp file`），以便检查并修改其日历设置。*

## 步骤 2：显示当前工作日属性
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
此代码打印当前的 **一周起始日**、**每月天数**、**每日分钟数** 和 **每周分钟数**——这些是你经常需要 **自定义项目日历** 的核心要素。

## 步骤 3：设置新的工作日属性
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
在此步骤中，我们 **将一周起始日** 设置为 Monday，**将每月天数** 更改为 24，并调整每日和每周的分钟数。当需要 **更新项目进度表** 以匹配非标准工作日历时，这些设置非常常见。

## 步骤 4：保存更新后的项目
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
修改后的项目以 XML 文件形式保存，便于共享或导入到其他工具中。

## 步骤 5：确认操作
```java
System.out.println("Process completed Successfully");
```
简单的控制台信息会告诉你工作流已顺利完成且没有错误。

## 常见问题与提示
- **文件路径不正确** – 确认 `dataDir` 以斜杠结尾，或使用 `Paths.get(...)` 以获得跨平台的路径。  
- **未设置许可证** – 在生产环境中，创建 `Project` 之前请调用 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`。  
- **意外的周起始日** – 确保使用正确的 `DayType` 枚举值（例如 `DayType.Sunday`）。  

## 常见问题

**Q: Aspose.Tasks for Java 能处理复杂的项目结构吗？**  
A: 能，Aspose.Tasks for Java 提供了全面的支持，能够轻松处理复杂的项目结构。

**Q: Aspose.Tasks for Java 是否兼容不同版本的 Microsoft Project 文件？**  
A: 当然，Aspose.Tasks for Java 支持多种版本的 Microsoft Project 文件，确保跨平台兼容性。

**Q: 我可以将 Aspose.Tasks for Java 集成到现有的 Java 应用程序中吗？**  
A: 可以，Aspose.Tasks for Java 提供无缝的集成能力，帮助你在 Java 应用中加入强大的项目管理功能。

**Q: Aspose.Tasks for Java 提供文档和支持吗？**  
A: 是的，你可以在其 [website](https://releases.aspose.com/) 上获取丰富的文档和社区支持。

**Q: 是否有 Aspose.Tasks for Java 的免费试用版？**  
A: 有，你可以从其 [website](https://reference.aspose.com/tasks/java/) 下载免费试用版，先行体验功能后再决定购买。

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
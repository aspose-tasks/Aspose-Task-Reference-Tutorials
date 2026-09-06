---
date: 2026-08-13
description: 了解如何使用 Aspose.Tasks 在 Java 中创建标准的 MS Project 日历。本分步指南展示了如何创建标准的 MS Project
  日历、将其设为默认并保存文件。
keywords:
- how to create calendar
- create ms project calendar
- aspose.tasks java calendar
- standard project calendar
lastmod: 2026-08-13
linktitle: 在 Aspose.Tasks 中创建标准日历
og_description: 如何在 Java 中使用 Aspose.Tasks 创建日历。了解如何快速构建标准的 MS Project 日历、将其设为默认，并在几分钟内保存项目文件。
og_image_alt: Developer guide showing Java code to create a standard Microsoft Project
  calendar using Aspose.Tasks
og_title: 如何创建日历 – 在 Aspose.Tasks 中创建标准日历
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  headline: How to create calendar – make standard calendar in Aspose.Tasks
  type: TechArticle
- description: Learn how to create a standard MS Project calendar in Java using Aspose.Tasks.
    This step‑by‑step guide shows you how to create a standard MS Project calendar,
    add it as the default, and save the file.
  name: How to create calendar – make standard calendar in Aspose.Tasks
  steps:
  - name: set up the data directory
    text: Define where the generated project file will be saved. Replace `"Your Data
      Directory"` with the absolute path on your machine (e.g., `C:/Projects/Output/`).
  - name: create a project instance
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Instantiating it gives you a container for calendars,
      tasks, resources, and other project data.'
  - name: define and make the calendar standard
    text: '`Calendar` is the class that models a working‑time schedule. Adding a new
      calendar named **“My Cal”** and calling `makeStandardCalendar` promotes it to
      the default calendar for the entire project. > **Pro tip:** The `makeStandardCalendar`
      method automatically marks the supplied calendar as the defau'
  - name: save the project
    text: SaveFileFormat is an enumeration that specifies the file format to use when
      saving a project. Persist the project (including the new calendar) to an XML
      file. You can change the file name or format (`SaveFileFormat.Pp`) if you prefer
      a different Project version.
  - name: display completion message
    text: Give yourself a visual cue that the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports a wide range of Microsoft Project versions,
      from 2000 up to the latest releases.
    question: Is Aspose.Tasks compatible with all versions of Microsoft Project?
  - answer: Absolutely! You can modify working days, add exceptions, and define specific
      working times using the `WeekDay` and `WorkingTime` classes.
    question: Can I customize the calendar settings further?
  - answer: Certainly. The library is designed for high‑performance, scalable environments
      and offers comprehensive support for large Project files.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, Aspose provides dedicated forums, ticket‑based support, and extensive
      documentation to help you resolve any issues quickly.
    question: Does Aspose.Tasks offer technical support for developers?
  - answer: Yes, you can explore a free trial version available on the [website](https://purchase.aspose.com/buy),
      allowing you to evaluate all features before committing.
    question: Can I try Aspose.Tasks before making a purchase?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar creation
- aspose.tasks
- java project management
title: 如何创建日历 – 在 Aspose.Tasks 中创建标准日历
url: /zh/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何创建日历 – 在 Aspose.Tasks 中创建标准日历

## 介绍
在本教程中，您将学习 **如何创建日历** 对象，为 Microsoft Project 文件使用 Aspose.Tasks for Java 库。我们将演示如何创建标准的 MS Project 日历、将其设为默认（标准）日历以及保存项目文件。完成本指南后，您将能够在任何基于 Java 的项目管理解决方案中集成日历创建功能。

## 快速答案
- **“standard calendar” 是什么意思？** 它是默认的工作时间定义，适用于未分配自定义日历的任务。  
- **需要哪个库？** Aspose.Tasks for Java – 一个纯 Java API，无需安装 Microsoft Project 即可工作。  
- **我需要许可证吗？** 免费试用可用于开发；生产部署需要商业许可证。  
- **生成的文件格式是什么？** 基于 XML 的 Microsoft Project 文件（`.xml`）。  
- **实现需要多长时间？** 基本日历设置大约需要 5‑10 分钟。

## 什么是 Microsoft Project 中的标准日历？
标准日历定义了项目的默认工作日和工作时间，通常为周一至周五，上午 8 点至下午 5 点。添加标准日历后，未分配自定义日历的任何任务都会继承这些工作时间，从而确保整个项目的调度保持一致。

## 为什么使用 Aspose.Tasks 来创建日历？
Aspose.Tasks for Java 支持 **50 多种输入和输出格式**，并且能够在不将整个文件加载到内存的情况下处理多达 **10,000 个任务** 的项目。这个纯 Java 库让您可以在服务器、CI 流水线或任何 Java 应用程序上自动化 Project 文件的创建，免除对已授权 Microsoft Project 的依赖。

## 前提条件
在开始之前，请确保以下条件已就绪：

### Java Development Kit (JDK) 安装
从 Oracle 网站或 OpenJDK 发行版安装最新的 JDK。

### Aspose.Tasks for Java 库
从 [download page](https://releases.aspose.com/tasks/java/) 下载库。将 JAR 添加到项目的 classpath 中。

## 导入包
本教程只需要一个导入语句：

```java
import com.aspose.tasks.*;
```

## 步骤指南

### 步骤 1：设置数据目录
定义生成的项目文件保存位置。

```java
String dataDir = "Your Data Directory";
```

将 `"Your Data Directory"` 替换为您机器上的绝对路径（例如，`C:/Projects/Output/`）。

### 步骤 2：创建项目实例
`Project` 是 Aspose.Tasks 的顶层对象，表示内存中的单个 Microsoft Project 文件。实例化它后，您将获得一个用于存放日历、任务、资源及其他项目数据的容器。

```java
Project project = new Project();
```

### 步骤 3：定义并设为标准日历
`Calendar` 是用于建模工作时间表的类。添加一个名为 **“My Cal”** 的新日历并调用 `makeStandardCalendar`，即可将其提升为整个项目的默认日历。

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **技巧提示：** `makeStandardCalendar` 方法会自动将提供的日历标记为项目的默认日历，这正是您在需要 **添加标准日历** 功能时所需的。

### 步骤 4：保存项目
SaveFileFormat 是一个枚举，用于指定保存项目时使用的文件格式。  
将项目（包括新日历）持久化为 XML 文件。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

如果您想使用不同的 Project 版本，可以更改文件名或格式（`SaveFileFormat.Pp`）。

### 步骤 5：显示完成信息
给自己一个可视化提示，表明过程已成功完成且没有错误。

```java
System.out.println("Process completed Successfully");
```

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **文件未找到** | `dataDir` 指向一个不存在的文件夹 | 创建该文件夹或使用绝对路径 |
| **许可证异常** | 在生产环境中未使用有效的 Aspose.Tasks 许可证运行 | 通过 `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 应用许可证文件 |
| **空日历** | 忘记添加工作时间定义 | 如果需要自定义工作时间，请使用 `cal1.getWeekDays().add(WeekDay.DayType.Monday)` 等方法 |

## 常见问题

**问：Aspose.Tasks 是否兼容所有版本的 Microsoft Project？**  
答：是的，Aspose.Tasks 支持广泛的 Microsoft Project 版本，从 2000 版一直到最新发布的版本。

**问：我可以进一步自定义日历设置吗？**  
答：当然可以！您可以使用 `WeekDay` 和 `WorkingTime` 类修改工作日、添加例外并定义特定的工作时间。

**问：Aspose.Tasks 适用于企业级应用吗？**  
答：当然。该库专为高性能、可扩展的环境设计，并提供对大型 Project 文件的全面支持。

**问：Aspose.Tasks 为开发者提供技术支持吗？**  
答：是的，Aspose 提供专门的论坛、基于工单的支持以及丰富的文档，帮助您快速解决任何问题。

**问：我可以在购买前试用 Aspose.Tasks 吗？**  
答：可以，您可以在 [website](https://purchase.aspose.com/buy) 上获取免费试用版，先评估所有功能再决定。

---

**最后更新：** 2026-08-13  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Tasks for Java 将日历添加到项目](/tasks/java/calendars/create/)
- [使用 Aspose.Tasks 在 Java 中设置项目日历](/tasks/java/calendars/properties/)
- [使用 Aspose.Tasks for Java 创建自定义日历例外](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
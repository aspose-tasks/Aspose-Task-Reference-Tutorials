---
date: 2026-08-03
description: 了解如何使用 Aspose.Tasks for Java 创建 ms project 日历、将日历添加到项目中，并将项目保存为 XML。
keywords:
- create ms project calendar
- Aspose.Tasks Java
- project calendar automation
lastmod: 2026-08-03
linktitle: 使用 Aspose.Tasks 将日历添加到项目
og_description: 使用 Aspose.Tasks for Java 以编程方式创建 ms project 日历。添加日历、定制计划，并在几分钟内导出为
  XML。
og_image_alt: Guide to creating MS Project calendar with Aspose.Tasks Java API
og_title: 使用 Aspose.Tasks for Java 创建 ms project 日历
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  headline: Create ms project calendar with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create ms project calendar, add calendar to a project,
    and save the project as XML using Aspose.Tasks for Java.
  name: Create ms project calendar with Aspose.Tasks for Java
  steps:
  - name: import the required Aspose.Tasks package
    text: First, bring the Aspose.Tasks classes into scope so you can work with projects
      and calendars.
  - name: set the data directory path
    text: Define where the generated project file will be written. Replace the placeholder
      with an absolute or relative path on your machine.
  - name: create a new Project instance
    text: '`Project` is the core class that represents a Microsoft Project file in
      memory.'
  - name: define the calendars you want to add
    text: '`Calendar` defines a schedule with working days, exceptions, and working
      times for a project. > **Pro tip:** After adding a calendar, you can customize
      its working days with `cal1.getWeekDays().add(...)` and set daily work hours
      using `cal1.getBaseCalendar().setWorkingTime(...)`.'
  - name: save the project (save project as XML)
    text: '`SaveFileFormat.Xml` tells Aspose.Tasks to write the project in XML format.'
  - name: display a completion message
    text: Let the user know the operation finished successfully. By following these
      six concise steps, you have successfully **added a calendar to a project** and
      saved the result as an XML file.
  type: HowTo
- questions:
  - answer: Yes – after adding a calendar you can define exceptions, working hours,
      and non‑working days using the `WeekDay` and `Exception` classes.
    question: Can Aspose.Tasks handle complex calendars with multiple exceptions?
  - answer: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task
      Name")` and set `task.set(Tsk.CALENDAR, cal3);`.
    question: Is it possible to assign the new calendar to specific tasks?
  - answer: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6`
      as needed; Aspose.Tasks supports **12** output formats.
    question: Does the library support saving in other formats like MPP?
  - answer: A temporary evaluation license is sufficient for testing; a full license
      is required for production deployments.
    question: Do I need a license for development builds?
  - answer: 'The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks
      forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I get help if I run into issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create ms project calendar
- Aspose.Tasks
- Java project management
title: 使用 Aspose.Tasks for Java 创建 ms project 日历
url: /zh/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 ms project 日历 使用 Aspose.Tasks for Java

## 介绍
在现代项目管理工作流中，能够以编程方式**创建 ms project 日历**可以节省大量手动编辑的时间。Aspose.Tasks for Java 为您提供了一个干净、类型安全的 API 来操作 Microsoft Project 文件，而无需打开桌面客户端。在本教程中，您将学习如何添加日历、如何创建 MS Project 日历以及如何将项目保存为 XML——只需几行 Java 代码。

## 快速答案
- **“创建 ms project 日历”是什么意思？**  
  指通过代码向 Microsoft Project 文件中插入一个新的工作时间定义（日历）。  
- **哪个库负责此功能？**  
  Aspose.Tasks for Java 提供 `Calendar` 类和 `Project` 容器来管理日历。  
- **我需要许可证吗？**  
  临时评估许可证可用于测试；生产环境需要完整许可证。  
- **我可以将文件保存为 XML 吗？**  
  可以——使用 `SaveFileFormat.Xml` 将项目导出为 XML 文件。  
- **前置条件是什么？**  
  Java JDK 8+ 和 Aspose.Tasks for Java JAR 已加入您的类路径。

## 什么是创建 ms project 日历？
创建 MS Project 日历是指以编程方式向 Project 文件添加新的日历定义，指定工作日、例外以及每日工作时间，然后将该日历分配给任务、资源或整个项目，使调度计算遵循定义的工作时间。

## 为什么使用 Aspose.Tasks for Java 向项目添加日历？
您应该使用 Aspose.Tasks for Java，因为它提供了完全类型安全的 API，无需安装 Microsoft Project，即可工作，支持所有主要的 Project 版本（2007‑2021，覆盖 5+ 版本），并且可以导出为 XML、MPP 和 **10+** 其他格式，实现任何服务器上的自动批量日历创建。

## 前置条件
- **Java Development Kit (JDK) 8 或更高版本** 已安装并配置。  
- **Aspose.Tasks for Java** 库——从[官方站点](https://releases.aspose.com/tasks/java/)下载并将 JAR 添加到项目的类路径。  
- 您选择的 IDE 或构建工具（Maven/Gradle）。

## 步骤指南

### 步骤 1：导入所需的 Aspose.Tasks 包
首先，将 Aspose.Tasks 类导入作用域，以便您可以处理项目和日历。

```java
import com.aspose.tasks.*;
```

### 步骤 2：设置数据目录路径
定义生成的项目文件将写入的位置。将占位符替换为您机器上的绝对或相对路径。

```java
String dataDir = "Your Data Directory";
```

### 步骤 3：创建新的 Project 实例
`Project` 是表示内存中 Microsoft Project 文件的核心类。

```java
Project prj = new Project();
```

### 步骤 4：定义要添加的日历
`Calendar` 定义了项目的工作日、例外和工作时间表。

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **专业提示：** 添加日历后，您可以使用 `cal1.getWeekDays().add(...)` 自定义其工作日，并使用 `cal1.getBaseCalendar().setWorkingTime(...)` 设置每日工作时间。

### 步骤 5：保存项目（将项目保存为 XML）
`SaveFileFormat.Xml` 告诉 Aspose.Tasks 将项目以 XML 格式写入。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 步骤 6：显示完成消息
让用户知道操作已成功完成。

```java
System.out.println("Process completed Successfully");
```

通过遵循这六个简洁步骤，您已成功**向项目添加日历**并将结果保存为 XML 文件。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **`NullPointerException` on `prj.getCalendars()`** | 项目对象未正确初始化。 | 确保在访问日历之前调用 `new Project()`。 |
| **保存时文件未找到** | `dataDir` 指向不存在的文件夹。 | 首先创建目录或使用绝对路径。 |
| **日历名称显示为 “no info”** | 示例中使用了占位名称。 | 用能反映日程的有意义名称替换（例如 “US Holiday Calendar”）。 |
| **保存的 XML 无法在 MS Project 中打开** | 使用了过时的 Aspose.Tasks 版本。 | 更新到最新的 Aspose.Tasks for Java 发行版。 |

## 常见问答

**问：Aspose.Tasks 能处理带有多个例外的复杂日历吗？**  
答：可以——添加日历后，您可以使用 `WeekDay` 和 `Exception` 类定义例外、工作时间和非工作日。

**问：是否可以将新日历分配给特定任务？**  
答：完全可以。通过 `prj.getRootTask().getChildren().add("Task Name")` 获取任务，并设置 `task.set(Tsk.CALENDAR, cal3);`。

**问：库是否支持以其他格式（如 MPP）保存？**  
答：支持。将 `SaveFileFormat.Xml` 替换为 `SaveFileFormat.Mpp` 或 `SaveFileFormat.P6` 即可；Aspose.Tasks 支持 **12** 种输出格式。

**问：开发构建是否需要许可证？**  
答：临时评估许可证足以用于测试；生产部署需要完整许可证。

**问：如果遇到问题，在哪里可以获取帮助？**  
答：Aspose.Tasks 社区论坛是极好的资源：[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)。

---

**最后更新：** 2026-08-03  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何在 MS Project 日历中定义工作日 – Aspose.Tasks Java](/tasks/java/calendars/)
- [如何使用 Aspose.Tasks 设置项目日历 Java](/tasks/java/calendars/properties/)
- [使用 Aspose.Tasks for Java 创建自定义日历例外](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
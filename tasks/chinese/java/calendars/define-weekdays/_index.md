---
date: 2026-08-08
description: 了解如何使用 Aspose.Tasks for Java 设置 MS Project 日历、设定每日工作时间并添加周末工作日。只需几行代码即可将项目保存为
  XML。
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: 如何在 MS Project 中设置日历并定义工作日
og_description: 使用 Aspose.Tasks for Java 设置 MS Project 日历、定义工作日并添加周末工作日。按照本分步教程操作，并保存为
  XML。
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: 使用 Aspose.Tasks 设置 MS Project 日历 – Java 指南
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: 如何在 MS Project 中设置日历并定义工作日
url: /zh/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何设置 MS Project 日历并定义工作日

在本教程中，您将学习 **如何设置 MS Project 日历**，以编程方式定义工作日，并使用 Aspose.Tasks for Java 库配置自定义工作日。无论您是构建调度引擎、与 ERP 系统集成，还是仅需在不打开 Microsoft Project 的情况下生成项目计划，下面的步骤将展示如何创建日历、设置每日工作时间以及在几行代码中添加周末工作日。

## 快速答案
- **需要哪个库？** Aspose.Tasks for Java.  
- **我可以添加周末工作日吗？** 是的——只需将星期六和星期日标记为工作日。  
- **如何保存项目？** 调用 `prj.save(..., SaveFileFormat.Xml)`。  
- **需要许可证吗？** 免费试用可用于评估；生产使用需要许可证。  
- **支持哪个 Java 版本？** Java 8 或更高。

## 什么是设置 MS Project 日历？
在 MS Project 中设置日历决定哪些天被视为工作日、每天的工作小时数以及诸如假期或全公司停工等特殊例外。此信息驱动任务调度、资源分配和整体项目时间表，确保计算符合组织的实际工作模式。

## 为什么使用 Aspose.Tasks 进行日历操作？
Aspose.Tasks 让您无需启动 Microsoft Project UI 即可以编程方式控制日历。它可在任何支持 Java 的操作系统上运行，支持超过 50 种输入和输出格式，并且能够在不将整个文件加载到内存的情况下处理数百页的项目，使其非常适合服务器端自动化。

## 前提条件
- **Java Development Kit (JDK) 8+** – 从 [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下载。  
- **Aspose.Tasks for Java** – 从 [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) 获取最新的 JAR。  
- 一个 IDE 或构建工具（Maven/Gradle），用于将 Aspose.Tasks JAR 添加到类路径。

## 导入包
导入提供对项目、日历和工作时间对象访问的类。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## 步骤指南

### 步骤 1：创建项目实例
实例化一个 `Project` 对象，它代表您将要操作的 MS Project 文件。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### 步骤 2：定义新日历
`Calendar` 表示项目的一组工作时间、例外和假期。

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### 步骤 3：添加标准工作日（星期一‑星期四）
`WeekDay` 定义一周中某一天的工作时间。

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### 步骤 4：添加周末工作日
如果您的项目在周末运行，请将星期六和星期日添加为常规工作日。这演示了 **添加周末工作日**。

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### 步骤 5：设置自定义短工作日（星期五）
为星期五配置上午班（9 am‑12 pm）和下午班（1 pm‑4 pm），以演示 **设置每日工作时间** 和自定义短工作日。

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### 步骤 6：将项目保存为 XML
`SaveFileFormat` 列举了保存项目时支持的文件格式，例如 XML 或 MPP。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 常见问题与解决方案

| 问题 | 解决方案 |
|-------|----------|
| **工作时间未应用** | 确保在每个自定义 `WeekDay` 上调用 `setDayWorking(true)`。 |
| **保存时未找到文件** | 验证 `dataDir` 指向一个存在的文件夹，并且应用程序具有写入权限。 |
| **日历未在任务中体现** | 使用 `task.setCalendar(cal)` 将新创建的日历分配给资源或任务。 |

## 常见问题

**Q: 我可以使用 Aspose.Tasks for Java 定义自定义非工作日吗？**  
A: 是的。将任何您想设为非工作日的 `WeekDay` 的 `DayWorking` 属性设为 `false`。

**Q: 我如何添加假期或全公司例外？**  
A: 创建 `CalendarException` 对象，指定例外日期，并将其添加到 `cal.getExceptions()`。

**Q: 该库是否兼容旧版 MS Project？**  
A: 当然。Aspose.Tasks 支持多个 Project 版本的 MPP、MPT 和 XML 格式。

**Q: 我可以修改导入项目中的现有日历吗？**  
A: 使用 `new Project("existing.mpp")` 加载项目，获取所需的日历，进行修改后保存。

**Q: Aspose.Tasks 也能处理循环任务吗？**  
A: 可以，您可以使用 `RecurringTask` 类创建和编辑循环任务。

## 结论
现在您已经了解 **如何设置 MS Project 日历**，定义工作日，添加周末工作日，并配置简短的星期五日程——全部使用 Aspose.Tasks for Java。将结果保存为 XML，并将日历逻辑集成到任何基于 Java 的项目管理解决方案中。

---

**最后更新:** 2026-08-08  
**测试版本:** Aspose.Tasks for Java 24.11  
**作者:** Aspose

## 相关教程

- [使用 Aspose.Tasks for Java 将日历添加到项目](/tasks/java/calendars/create/)
- [使用 Aspose.Tasks 确定工作日和工作时间](/tasks/java/calendars/working-hours/)
- [使用 Aspose.Tasks 将假期添加到日历并保存为 MPP](/tasks/java/calendars/update-to-mpp/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: 2026-07-29
description: 了解如何通过使用 Aspose.Tasks for Java 创建项目日历来安排非工作日，定义工作日例外并管理假期计划。
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: 安排非工作日 – 创建项目日历 Aspose
og_description: 使用 Aspose.Tasks for Java 安排非工作日。了解如何定义工作日、添加日历例外以及高效管理假期计划。
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: 安排非工作日 – 创建项目日历 Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-29'
  description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  headline: Schedule Non Working Days – Create Project Calendar Aspose
  type: TechArticle
- description: Learn how to schedule non working days by creating a project calendar
    with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
  name: Schedule Non Working Days – Create Project Calendar Aspose
  steps:
  - name: Import Required Packages
    text: We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for
      date handling.
  - name: Define the Data Directory
    text: Specify where the generated project file will be saved.
  - name: Create a Project Instance
    text: '`Project` is the main object that holds all project data, including tasks,
      resources, and calendars.'
  - name: Define a Calendar
    text: '`Calendar` represents a schedule of working and non‑working times within
      a project.'
  - name: Define Weekdays Exception
    text: '`CalendarException` represents a period that is marked as non‑working in
      a calendar.'
  - name: Save the Project
    text: Persist the project, including the custom calendar and its exception, to
      an XML file.
  type: HowTo
- questions:
  - answer: Yes. Add additional `CalendarException` objects to `cal.getExceptions()`
      for each distinct period or rule.
    question: Can I define multiple exceptions for different weekdays within the same
      calendar?
  - answer: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and
      any IDE that supports standard Java projects.
    question: Is Aspose.Tasks for Java compatible with different Java IDEs?
  - answer: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit
      your scheduling needs.
    question: Can I customize exception types other than daily exceptions?
  - answer: Build the exception objects programmatically—e.g., read holiday dates
      from a database or configuration file and create `CalendarException` instances
      in a loop.
    question: How can I handle exceptions dynamically based on project requirements?
  - answer: Yes, you can download a free trial from the [Aspose.Tasks Java download
      page](https://releases.aspose.com/tasks/java/).
    question: Is there a trial version available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- schedule non working days
- Aspose.Tasks
- Java calendar exceptions
- project calendar
- non-working days
title: 安排非工作日 – 创建项目日历 Aspose
url: /zh/java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 安排非工作日 – 创建项目日历 Aspose

### 简介
当您需要为项目 **安排非工作日** 时，必须能够在项目计划中直接对假期、特殊班次或临时关闭进行建模。Aspose.Tasks for Java 为您提供对日历定义的完整控制，允许您添加反映真实世界时间表的例外。在本教程中，我们将逐步演示如何为日历例外定义工作日，以确保项目时间线保持准确可靠。完成后，您还将看到这如何适用于任何企业项目的更广泛 **非工作日安排** 策略。

## 快速回答
- **“安排非工作日”是什么意思？**  
  这意味着使用 Aspose.Tasks 创建一个日历，将特定日期标记为非工作日，从而自动影响任务日期。  
- **运行示例是否需要许可证？**  
  免费试用可用于开发；生产环境需要商业许可证。  
- **支持哪些 IDE？**  
  IntelliJ IDEA, Eclipse, NetBeans, or any IDE that supports Java 8+.  
- **我可以向同一个日历添加多个例外吗？**  
  是的——您可以根据需要添加任意数量的 `CalendarException` 对象。  
- **我可以将项目保存为何种文件格式？**  
  XML, MPP, and several other formats supported by Aspose.Tasks.  

## 什么是 Aspose.Tasks 中的项目日历？
**project calendar** 是 Aspose.Tasks 的顶层对象，用于定义项目的工作日和工作时间。它直接影响任务的开始/结束日期、资源分配以及整体进度计算。通过自定义日历，您可以确保进度遵循真实世界的约束，例如公司假期或周末工作政策。

## 为什么要为日历例外定义工作日？
定义工作日例外可确保项目引擎将这些天视为非工作日，防止任务自动安排在这些天上，并使时间线与真实世界的约束（如假期、维护窗口或组织内的特殊班次模式）保持一致。

- **准确的时间线：** 任务不会被安排在假期或停工期间。  
- **资源规划：** 资源仅在有效工作日分配，防止超额分配。  
- **合规性：** 进度自动遵循组织政策或法定假期日历。  

## 使用日历例外的非工作日安排
当您维护 **非工作日安排** 时，通常会有一份假期、维护窗口或其他停工期间的主列表。将这些日期添加为 `CalendarException` 对象可确保每一次计算——无论是关键路径分析还是资源平衡——都自动遵守这些约束。此方法消除手动日期调整，降低进度漂移的风险。

## 先决条件
1. **Java Development Kit (JDK)** – 版本 8 或更高。  
2. **Aspose.Tasks for Java** – 从官方 [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) 下载。  
3. **An IDE** – IntelliJ IDEA、Eclipse、NetBeans，或任何兼容 Java 的编辑器。  

## 如何使用日历例外安排非工作日
加载项目，创建自定义日历，并添加将所需工作日标记为非工作日的 `CalendarException` 对象。整个过程可以通过少数几个简明步骤完成，生成的日历将自动影响所有任务调度逻辑。

### 分步指南

### 步骤 1：导入所需包
我们需要核心的 Aspose.Tasks 类以及 Java 的 `GregorianCalendar` 来处理日期。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### 步骤 2：定义数据目录
指定生成的项目文件保存的位置。

```java
String dataDir = "Your Data Directory";
```

### 步骤 3：创建 Project 实例
`Project` 是保存所有项目数据的主要对象，包括任务、资源和日历。

```java
Project project = new Project();
```

### 步骤 4：定义日历
`Calendar` 表示项目内部的工作和非工作时间表。

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### 步骤 5：定义工作日例外
`CalendarException` 表示在日历中标记为非工作期的时间段。

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### 步骤 6：保存项目
将项目（包括自定义日历及其例外）持久化为 XML 文件。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **例外日期未应用** | 确保 `setEnteredByOccurrences(false)` 并使用正确的 `FromDate/ToDate` 值。 |
| **保存的文件为空** | 验证 `dataDir` 指向可写文件夹且文件名以 `.xml` 结尾。 |
| **日历未在任务调度中体现** | 使用 `task.setCalendar(cal)` 或 `resource.setCalendar(cal)` 将日历分配给任务或资源。 |

## 常见问题
**Q: 我可以在同一个日历中为不同的工作日定义多个例外吗？**  
A: 是的。为每个不同的期间或规则向 `cal.getExceptions()` 添加额外的 `CalendarException` 对象。

**Q: Aspose.Tasks for Java 是否兼容不同的 Java IDE？**  
A: 完全兼容。该库可在 IntelliJ IDEA、Eclipse、NetBeans 以及任何支持标准 Java 项目的 IDE 中使用。

**Q: 我可以自定义除每日例外之外的例外类型吗？**  
A: 可以。使用 `CalendarExceptionType.Weekly`、`Monthly` 或 `Yearly` 来满足您的调度需求。

**Q: 如何根据项目需求动态处理例外？**  
A: 可以通过编程方式构建例外对象——例如，从数据库或配置文件读取假期日期，并在循环中创建 `CalendarException` 实例。

**Q: Aspose.Tasks for Java 是否提供试用版？**  
A: 是的，您可以从 [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/) 下载免费试用版。

## 结论
通过遵循这些步骤，您现在了解如何通过创建项目日历并定义准确反映假期或特殊非工作期间的工作日例外来 **安排非工作日**。正确的日历配置对于实现真实的进度、资源分配和整体项目成功至关重要。进一步探索，可将自定义日历附加到任务或资源，并尝试其他例外类型，以为任何项目构建完整的 **非工作日安排**。

---

**最后更新:** 2026-07-29  
**测试环境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose

## 相关教程

- [使用 Aspose.Tasks for Java 将日历添加到项目](/tasks/java/calendars/create/)
- [在 Aspose for Java 中创建日历例外](/tasks/java/calendar-exceptions/add-remove/)
- [如何在 MS Project 中使用 Aspose.Tasks 设置日历并定义工作日](/tasks/java/calendars/define-weekdays/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
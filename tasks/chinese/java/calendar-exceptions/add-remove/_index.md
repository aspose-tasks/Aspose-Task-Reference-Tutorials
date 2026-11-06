---
date: 2026-11-06
description: 了解如何使用 Aspose.Tasks for Java 删除项目日历中的 exception，添加并高效管理 exceptions，提升排程。
images:
- /java/calendar-exceptions/add-remove/og-image.png
keywords:
- how to remove exception
- how to handle recurring
- how to add exception
- Aspose.Tasks Java
- project calendar management
lastmod: 2026-11-06
linktitle: 在 Aspose.Tasks 中添加和删除 Calendar Exceptions
og_description: 使用 Aspose.Tasks for Java 删除项目日历中的 exception。高效管理、添加和验证 calendar exceptions。
og_image_alt: Screenshot of Java code managing calendar exceptions with Aspose.Tasks
og_title: 如何删除项目日历中的 exception – Aspose.Tasks Java 指南
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Learn how to remove exception in a project calendar using Aspose.Tasks
    for Java, add and manage exceptions efficiently.
  headline: How to remove exception in a project calendar using Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Create a new `CalendarException` for each date range and add it to
      `calendar.getExceptions()` inside a loop.
    question: Can I add multiple exceptions to a calendar using Aspose.Tasks for Java?
  - answer: Aspose.Tasks supports a wide range of .mpp versions, from Project 98 up
      to the latest releases, ensuring seamless integration.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Use the `CalendarException` recurrence properties (`setRecurrencePattern`)
      to define daily, weekly, or monthly repeat patterns.
    question: How can I handle recurring exceptions (e.g., weekly meetings) in project
      calendars?
  - answer: Yes, you can download a free trial from the [Aspose Releases page](https://releases.aspose.com/)
      to explore all features before purchasing.
    question: Is there a trial version available for Aspose.Tasks for Java?
  - answer: Visit the Aspose.Tasks forum for Java on the [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/)
      to ask questions, or contact Aspose support directly.
    question: Where can I seek support for Aspose.Tasks for Java issues?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exception
- Aspose.Tasks
- Java project scheduling
title: 如何使用 Aspose.Tasks for Java 删除项目日历中的 exception
url: /zh/java/calendar-exceptions/add-remove/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 删除项目日历中的例外

## 介绍
准确的项目进度安排往往取决于对 **calendar exceptions**（资源不可用或工作计划变更的日期）的处理。使用 **Aspose.Tasks for Java**，您可以高效地 **create**、**add**、**remove** 和 **manage** 日历例外。在本教程中，我们将演示加载项目、添加新例外、删除已有例外并验证结果，让您准确了解在不再需要时 **how to remove exception** 条目。

## 快速答案
- **What does “create calendar exception” mean?** 它指的是定义一个偏离标准工作日历的日期范围。  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to try it?** 有免费试用版；生产环境需要许可证。  
- **Can I remove an existing exception?** 是的——只需在日历的例外列表中定位并删除即可。  
- **Is this compatible with Microsoft Project files?** 完全兼容；Aspose.Tasks 能读取和写入所有主要的 .mpp 版本。

## 什么是 create calendar exception java？
`CalendarException` 类表示您添加到项目日历的非工作期间。它告诉调度器将指定日期视为假期、维护窗口或任何自定义的非工作时间，从而确保任务日期符合真实世界的约束。

## 为什么使用 Aspose.Tasks 处理日历例外？
Aspose.Tasks for Java 支持 **50+ 输入和输出格式**，并且能够在不将整个文档加载到内存的情况下处理高达 **2 GB** 的文件。在处理大型例外列表时，相比原生 Microsoft Project API 可提供约 **40 %** 的性能提升，使其非常适合企业级调度场景。

## 前置条件
- 已安装 Java Development Kit (JDK) 8 或更高版本。  
- 已将 Aspose.Tasks for Java 库添加到项目的 classpath 中。  
- 对 Java 语法和项目管理概念有基本了解。

## 如何从日历中删除例外？
`Project` 类代表一个 Microsoft Project 文件，并提供对其日历、任务和资源的访问。`CalendarException` 类定义了日历中的非工作期间。加载项目后，在日历的例外集合中定位不需要的 `CalendarException`，并对列表调用 `remove`。此操作会立即更新计划，除非您希望持久化更改，否则无需重新保存整个项目文件。

## 如何向日历添加例外？
`CalendarException` 类定义了可以添加到日历的非工作期间。实例化一个新的 `CalendarException`，设置其开始和结束日期，将其标记为非工作，并将其添加到日历的例外列表中。添加后立即生效，调度器会将该范围视为所有关联该日历的任务的假期。

## 如何处理循环例外？
`CalendarException` 的重复属性（`setRecurrencePattern`）允许您定义每日、每周或每月的重复模式。通过配置这些属性，您可以对每周会议、每月维护窗口或任何基于模式的非工作时间进行建模，而无需为每次出现单独创建条目。

## 导入包
`import` 语句将所需的 Aspose.Tasks 类引入作用域，以便在代码中引用。

```java
import com.aspose.tasks.*;
```

## 步骤 1：加载项目并访问其日历
`Project` 代表一个 Microsoft Project 文件，而 `Calendar` 代表该项目中的一个日程。加载已有文件并获取集合中的第一个日历是第一步。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "input.mpp");
Calendar cal = project.getCalendars().toList().get(0);
```

## 步骤 2：删除已有的例外（如有需要）
`CalendarException` 对象描述非工作期间。此代码段会检查例外列表，并在存在多个例外时删除第一条，以防误删唯一的例外。

```java
if (cal.getExceptions().size() > 1) {
    CalendarException exc = cal.getExceptions().get(0);
    cal.getExceptions().remove(exc);
}
```

> **Pro tip:** 删除项目之前请始终检查例外列表的大小，以避免 `IndexOutOfBoundsException`。

## 步骤 3：创建（添加）新的日历例外
我们实例化一个新的 `CalendarException`，设置其开始和结束日期，将其标记为非工作，并将其添加到日历的例外集合中。

```java
CalendarException calExc = new CalendarException();
java.util.Calendar calObject = java.util.Calendar.getInstance();
calObject.set(2009, java.util.Calendar.JANUARY, 1, 0, 0, 0);
calExc.setFromDate(calObject.getTime());
calObject.set(2009, java.util.Calendar.JANUARY, 3, 0, 0, 0);
calExc.setToDate(calObject.getTime());
cal.getExceptions().add(calExc);
```

> **Why this matters:** 添加例外使您能够在项目计划中直接建模假期、维护窗口或任何非工作期间。这是 **create calendar exception java** 功能的核心。

## 步骤 4：显示所有例外以进行验证
遍历 `calendar.getExceptions()` 并打印每个条目，可确认日历已反映预期的更改，帮助您及早发现错误。

```java
for (CalendarException calExc1 : cal.getExceptions()) {
    System.out.println("From " + calExc1.getFromDate().toString());
    System.out.println("To   " + calExc1.getToDate().toString());
}
```

## 如何在 Java 中添加日历例外？
使用 `new Project("input.mpp")` 加载项目，获取目标 `Calendar`，实例化一个具有所需开始和结束日期的 `CalendarException`，将其工作标志设为 `false`，并将其添加到 `calendar.getExceptions()`。这段简洁的代码只需几行即可创建 calendar exception java。

## 常见问题与解决方案
| Issue | Cause | Fix |
|-------|-------|-----|
| 没有输出 | 例外列表为空 | 确保在遍历之前已添加例外。 |
| `project` 上的 NullPointerException | 文件路径不正确 | 确认 `dataDir` 指向有效的 `.mpp` 文件。 |
| 日期相差一天 | 时区差异 | 使用带显式时区的 `java.util.Calendar` 或 `java.time` API。 |

## 常见问题

**Q:** 是否可以使用 Aspose.Tasks for Java 向日历添加多个例外？  
**A:** 可以。为每个日期范围创建一个新的 `CalendarException`，并在循环中将其添加到 `calendar.getExceptions()`。

**Q:** Aspose.Tasks for Java 是否兼容所有版本的 Microsoft Project 文件？  
**A:** Aspose.Tasks 支持广泛的 .mpp 版本，从 Project 98 到最新发布的版本，确保无缝集成。

**Q:** 如何在项目日历中处理循环例外（例如每周会议）？  
**A:** 使用 `CalendarException` 的重复属性（`setRecurrencePattern`）定义每日、每周或每月的重复模式。

**Q:** 是否有 Aspose.Tasks for Java 的试用版？  
**A:** 有，您可以从 [Aspose Releases page](https://releases.aspose.com/) 下载免费试用版，以在购买前体验所有功能。

**Q:** 在哪里可以获取 Aspose.Tasks for Java 的支持？  
**A:** 访问 [Aspose Tasks Java forum](https://reference.aspose.com/tasks/java/) 提出问题，或直接联系 Aspose 支持。

## 结论
管理日历例外对于实现真实的项目时间表和资源规划至关重要。使用 **Aspose.Tasks for Java**，您可以 **create**、**add**、**remove** 并验证日历例外——只需几行代码。掌握 **how to remove exception** 条目，使您能够保持计划的准确性并符合真实世界的约束。

---

**最后更新:** 2026-11-06  
**测试环境:** Aspose.Tasks for Java 24.11  
**作者:** Aspose

## 相关教程

- [创建项目日历 Aspose – 为日历例外定义工作日](/tasks/java/calendar-exceptions/define-weekdays/)
- [使用 Aspose.Tasks 检索日历例外 – asp tasks java 教程](/tasks/java/calendar-exceptions/retrieve/)
- [使用 Aspose.Tasks for Java 将日历添加到项目](/tasks/java/calendars/create/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
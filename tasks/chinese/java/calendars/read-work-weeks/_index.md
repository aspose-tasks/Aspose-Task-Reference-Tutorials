---
date: 2026-08-13
description: 了解如何使用 Aspose.Tasks for Java 从 MS Project calendar 读取 workweeks。请按照包含
  code examples 和 troubleshooting tips 的 step‑by‑step guide 操作。
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: 使用 Aspose.Tasks 从 Calendar 读取 Work Weeks
og_description: 了解如何使用 Aspose.Tasks for Java 从 MS Project calendar 读取 workweeks。请按照包含
  setup steps、code snippets 和 troubleshooting tips 的 concise tutorial 操作。
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: 如何使用 Aspose.Tasks 从 MS calendar 读取 workweeks
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  headline: How to read workweeks from MS calendar with Aspose.Tasks
  type: TechArticle
- description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
    for Java. Follow the step‑by‑step guide with code examples and troubleshooting
    tips.
  name: How to read workweeks from MS calendar with Aspose.Tasks
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or later installed.'
    text: '**Java Development Kit (JDK)** – version 8 or later installed.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).'
  - name: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
    text: A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known
      folder on your machine.
  type: HowTo
- questions:
  - answer: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property
      setters to change names, dates, and working times.
    question: Can I modify the work weeks information using Aspose.Tasks for Java?
  - answer: Absolutely. It supports MPP files from Project 98 up to the latest releases,
      as well as Project XML files.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta
      EE, or any other framework.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: 'Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks
      trial](https://releases.aspose.com/).'
    question: Is there a trial version available for Aspose.Tasks?
  - answer: 'The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).'
    question: Where can I find support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read workweeks
- Aspose.Tasks
- Java project scheduling
- MS Project
- calendar API
title: 如何使用 Aspose.Tasks 从 MS calendar 读取 workweeks
url: /zh/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 从 MS 日历读取工作周

## 介绍
在本教程中，您将**学习如何读取工作周**，即使用 Aspose.Tasks Java 库从 Microsoft Project 日历中读取工作周。无论您是构建报表仪表板、与 ERP 系统同步计划，还是自动化分析的数据提取，程序化访问工作周定义都能节省大量手工时间。Aspose.Tasks 支持**50 多种输入和输出格式**，并且能够在不将整个文件加载到内存的情况下处理数百页的项目文件，为您提供灵活性和性能。

## 快速回答
- **“读取工作周”是什么意思？** 它指的是通过 Java 代码从 Project 文件中提取工作周定义（日期和每日工作时间规则）。  
- **需要哪个库？** Aspose.Tasks for Java（提供免费试用）。  
- **开发是否需要许可证？** 试用版可用于测试；生产部署需要商业许可证。  
- **支持哪些文件格式？** 同时处理 *.mpp* 和 Project XML 文件，另外还有 50 多种其他导入/导出格式。  
- **实现需要多长时间？** 在库设置完成后，通常不到 10 分钟。

## 在 MS Project 中，工作周是什么？
工作周定义了在特定期间资源可用的日历规则。它包括开始日期、结束日期以及每日工作时间间隔（例如，上午 9 点至下午 5 点）。在 MS Project 中，每个日历可以包含多个工作周，您可以用它来建模假期、轮班模式或季节性计划。

## Aspose.Tasks 如何从日历读取工作周？
Aspose.Tasks 提供了 `Calendar` 对象的 `WorkWeekCollection`。通过创建 `Project` 实例、选择所需的日历（通过 UID 或名称），并遍历其 `WorkWeekCollection`，您可以获取每个工作周的标签、生效日期范围以及详细的每日工作时间段。API 自动处理所有日期时间转换，并遵循项目的时区设置。

## 为什么要使用 Java 从 Microsoft Project 日历读取工作周？
以编程方式读取工作周可消除手动复制粘贴，确保下游系统（ERP、HR、报表）使用完全相同的调度规则，并保证多个项目之间的一致性。自动化还能降低人为错误并加快集成流水线，尤其是在您需要每晚处理数十个项目文件时。

## 前置条件
在深入代码之前，请确保您已具备以下条件：

1. **Java Development Kit (JDK)** – 已安装 8 版或更高版本。  
2. **Aspose.Tasks for Java** – 从官方网站下载最新的 JAR： [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)。  
3. 一个 **示例 Project 文件** (`ReadWorkWeeksInformation.mpp`)，放置在您机器上的已知文件夹中。

## 导入包
首先，导入我们需要用于与日历和工作周交互的类：

`Project` 代表一个 Microsoft Project 文件，`Calendar` 提供其日历，`WorkWeek` 定义工作周，`WeekDay` 代表一天。

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## 步骤 1：设置数据目录
定义包含 `.mpp` 文件的文件夹。将占位符替换为您机器上的实际路径：

```java
String dataDir = "Your Data Directory";
```

## 步骤 2：创建 Project 实例并访问日历
`Project` 类代表一个 Microsoft Project 文件，并提供对其数据结构的访问，包括日历、任务和资源。  
实例化一个 `Project` 对象，选择您想要的日历（通过 UID），并获取其 `WorkWeekCollection`：

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **专业提示：** 如果不确定日历 UID，可遍历 `project.getCalendars()`，先打印每个日历的名称和 UID。

## 步骤 3：遍历工作周
`WorkWeek` 类封装了工作周定义，包含开始/结束日期和每日工作时间设置。  
遍历每个 `WorkWeek`，显示其名称、开始/结束日期以及每日工作时间：

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**您将看到：** 控制台会打印每个工作周的标签（例如，“Standard”），其生效日期范围，并且您可以深入查看每一天的具体工作时间。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| `访问 calendar 时出现 NullPointerException` | UID 错误或日历不存在 | 使用 `project.getCalendars().size()` 验证 UID，并先列出可用的日历。 |
| 工作周无输出 | 所选日历没有自定义工作周（使用默认） | 使用默认日历 (`project.getDefaultCalendar()`) 或以编程方式创建工作周。 |
| 日期格式异常 | `System.out.println` 使用默认的 `java.util.Date` 格式 | 使用 `SimpleDateFormat` 按需格式化日期。 |

## 常见问答
**Q: 我可以使用 Aspose.Tasks for Java 修改工作周信息吗？**  
A: 可以。API 提供 `addWorkWeek()`、`removeWorkWeek()` 和属性设置器，以更改名称、日期和工作时间。

**Q: Aspose.Tasks 是否兼容不同版本的 Microsoft Project 文件？**  
A: 完全兼容。它支持从 Project 98 到最新版本的 MPP 文件，以及 Project XML 文件。

**Q: 我可以将 Aspose.Tasks 与其他 Java 框架集成吗？**  
A: 可以。该库是纯 Java 的，您可以与 Spring、Jakarta EE 或任何其他框架一起使用。

**Q: Aspose.Tasks 有试用版吗？**  
A: 有，您可以从官方网站下载免费 30 天试用版： [Aspose.Tasks trial](https://releases.aspose.com/)。

**Q: 在哪里可以找到 Aspose.Tasks 的支持？**  
A: Aspose 社区论坛是最佳地点： [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

**最后更新：** 2026-08-13  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Tasks for Java 将日历添加到项目](/tasks/java/calendars/create/)
- [使用 Aspose.Tasks 检索日历例外 – Aspose.Tasks Java 教程](/tasks/java/calendar-exceptions/retrieve/)
- [如何在 MS Project 中使用 Aspose.Tasks 设置日历并定义工作日](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
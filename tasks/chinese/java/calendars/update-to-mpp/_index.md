---
date: 2026-08-13
description: 了解如何将节假日添加到日历、将日历分配给项目，并使用 Aspose.Tasks for Java 将 MS Project 文件保存为 MPP。
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: 在 Aspose.Tasks 中将日历更新为 MPP 格式
og_description: 将节假日添加到日历、分配给项目，并使用 Aspose.Tasks for Java 将计划转换为 MPP。了解一步步的自动化过程。
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: 使用 Aspose.Tasks 将节假日添加到日历并保存为 MPP
schemas:
- author: Aspose
  dateModified: '2026-08-13'
  description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  headline: Add holidays to calendar and save as MPP with Aspose.Tasks
  type: TechArticle
- description: Learn how to add holidays to a calendar, assign the calendar to a project,
    and save the MS Project file as MPP using Aspose.Tasks for Java.
  name: Add holidays to calendar and save as MPP with Aspose.Tasks
  steps:
  - name: import required packages
    text: First, bring the Aspose.Tasks classes and Java utilities into scope.
  - name: set up the data directory
    text: Define where your input template and output files will live. Replace the
      placeholder with the actual path on your machine.
  - name: define input and output file names
    text: We’ll load an existing MPP file (or a blank project) and write the result
      to a new file.
  - name: load the project and add a new calendar
    text: '`Project` class represents an MS Project file in memory and provides access
      to its calendars, tasks, and resources. Create a `Project` instance from the
      source file and add a calendar named **“Calendar 1”**.'
  - name: customize the calendar (optional)
    text: '`Calendar` object defines working days, hours, and exceptions for a project
      schedule. If you need specific working times, holidays, or exceptions, call
      your own helper method. The sample uses `GetTestCalendar` as a placeholder.
      > **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set w'
  - name: assign the calendar to the project
    text: Tell the project to use the newly created calendar for all its scheduling
      calculations.
  - name: save the project as MPP
    text: '`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating
      native Microsoft Project format. Now **convert project to MPP** by saving it
      with the `SaveFileFormat.Mpp` option.'
  - name: confirm successful completion
    text: A simple console message lets you know the process finished without errors.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project
      2007 through Project 2024, covering more than 10 versions.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: Absolutely. You can define working days, set custom work weeks, add holidays,
      and even create multiple calendars within a single project file.
    question: Can I customize calendars according to specific project requirements?
  - answer: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?
  - answer: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Temporary licenses can be requested via the Aspose website [Aspose temporary
      license request](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays
- Aspose.Tasks
- Java project scheduling
title: 使用 Aspose.Tasks 将节假日添加到日历并保存为 MPP
url: /zh/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将假期添加到日历并使用 Aspose.Tasks 保存为 MPP

## 介绍

在现代项目管理中，您经常需要 **add holidays to calendar** 文件，创建 **MS Project calendar**，然后以原生 MPP 格式共享进度表。无论是整合多个来源的时间线还是迁移遗留数据，程序化生成日历都能消除手动错误并加快交付。本教程将带您完整了解在 MS Project 中创建日历、使用假期进行自定义、**assign calendar to project**，以及最终使用 Aspose.Tasks Java API **convert project to MPP** 的过程。

## 快速答复
- **What does this tutorial cover?** 添加假期到日历，将其分配给项目，并使用 Aspose.Tasks for Java 将结果保存为 MPP 文件。  
- **Do I need a license?** 免费试用可用于开发；生产环境需要商业许可证。  
- **Which Java version is required?** Java 8 或更高（JDK 8+）。  
- **Can I customize the calendar?** 是的——您可以添加工作时间、例外和假期。  
- **How long does implementation take?** 基本日历大约需要 10‑15 分钟。  

## 什么是 “create calendar MS Project”？

创建 calendar MS Project 意味着定义工作日、工作时间和例外，这些决定了 Microsoft Project 文件中任务的调度。使用 Aspose.Tasks，您可以以编程方式构建此日历、设置假期，并将其嵌入项目，而无需打开 MS Project UI。

## 为什么在此任务中使用 Aspose.Tasks？

您应该使用 Aspose.Tasks，因为它提供完整的 Java 兼容性，无需 Microsoft Office，并且可以直接从代码生成并保存原生 MPP 文件。该库支持所有日历功能，可在任何服务器环境中运行，并能在不到一秒的时间内处理多达 10,000 个任务的项目。

## 先决条件

1. **Java Development Kit (JDK) 8+** – 确保 `java -version` 报告 1.8 或更高。  
2. **Aspose.Tasks for Java** – 从 [Aspose website](https://releases.aspose.com/tasks/java/) 下载最新的 JAR。  
3. **IDE** – IntelliJ IDEA、Eclipse 或您喜欢的任何编辑器。  
4. **Basic Java knowledge** – 熟悉类、方法和文件 I/O。  

## 如何向日历添加假期

要添加假期，您需要创建一个新的 `Calendar` 对象，获取其 `Exceptions` 集合，并为每个假期日期添加 `DateException` 条目。`DateException` 表示日历中的单个非工作日期或范围。Aspose.Tasks 会将这些日期视为非工作日，确保任务围绕已定义的假期进行调度。

### 步骤 1：导入所需的包

首先，将 Aspose.Tasks 类和 Java 实用工具导入作用域。

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 步骤 2：设置数据目录

定义输入模板和输出文件的存放位置。将占位符替换为您机器上的实际路径。

```java
String dataDir = "Your Data Directory";
```

### 步骤 3：定义输入和输出文件名

我们将加载现有的 MPP 文件（或空白项目），并将结果写入新文件。

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 步骤 4：加载项目并添加新日历

`Project` 类在内存中表示 MS Project 文件，并提供对其日历、任务和资源的访问。

从源文件创建 `Project` 实例，并添加名为 **“Calendar 1”** 的日历。

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 步骤 5：自定义日历（可选）

`Calendar` 对象定义项目进度的工作日、工作时间和例外。

如果您需要特定的工作时间、假期或例外，请调用您自己的辅助方法。示例使用 `GetTestCalendar` 作为占位符。

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** 您可以直接操作 `cal1.getWeekDays()` 为每周的每一天设置工作时间，或使用 `cal1.getExceptions()` 来 **add holidays to calendar**。

### 步骤 6：将日历分配给项目

告诉项目使用新创建的日历进行所有调度计算。

```java
project.set(Prj.CALENDAR, cal1);
```

### 步骤 7：将项目保存为 MPP

`SaveFileFormat` 枚举指定输出格式，`Mpp` 表示原生 Microsoft Project 格式。

现在通过使用 `SaveFileFormat.Mpp` 选项保存，**convert project to MPP**。

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 步骤 8：确认成功完成

一个简单的控制台消息会告诉您该过程已成功完成且没有错误。

```java
System.out.println("Process completed Successfully");
```

## 常见用例

- **Automated schedule generation** 用于重复项目的自动进度生成（例如，每周冲刺）。  
- **Migrating legacy CSV or Excel calendars** 将传统的 CSV 或 Excel 日历迁移到功能完整的 MS Project 文件中。  
- **Server‑side reporting** 在需要时，Web 服务返回 MPP 文件的服务器端报告。  

## 故障排除与常见陷阱

| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` 指向不存在的文件夹 | 确保目录存在，或通过代码创建它。 |
| Calendar not applied to tasks | 任务仍然引用默认日历 | 在设置 `Prj.CALENDAR` 后，如果任务之前被覆盖，还需要更新每个任务的 `Task.CALENDAR`。 |
| Output file is 0 KB | 缺少写入权限 | 以适当的文件系统权限运行 JVM，或选择可写路径。 |

## 常见问题

**Q: Aspose.Tasks for Java 是否兼容不同版本的 MS Project？**  
A: 是的，Aspose.Tasks 支持从 Project 2007 到 Project 2024 的所有 Microsoft Project 文件格式，覆盖超过 10 个版本。

**Q: 我可以根据特定项目需求自定义日历吗？**  
A: 当然可以。您可以定义工作日、设置自定义工作周、添加假期，甚至在单个项目文件中创建多个日历。

**Q: Aspose.Tasks for Java 是否提供故障排除和帮助支持？**  
A: 是的，您可以在 Aspose.Tasks 社区论坛获取帮助 [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)。

**Q: 是否有 Aspose.Tasks for Java 的免费试用？**  
A: 有，提供功能完整的免费试用 [Aspose.Tasks free trial](https://releases.aspose.com/)。

**Q: 如何获取 Aspose.Tasks for Java 的临时许可证？**  
A: 可通过 Aspose 网站请求临时许可证 [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**最后更新:** 2026-08-13  
**测试使用:** Aspose.Tasks for Java 24.12  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.Tasks for Java 将日历添加到项目](/tasks/java/calendars/create/)
- [如何在 MS Project 日历中定义工作日 – Aspose.Tasks Java](/tasks/java/calendars/)
- [使用 Aspose.Tasks for Java 创建自定义日历例外](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
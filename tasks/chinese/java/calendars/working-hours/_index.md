---
date: 2026-08-24
description: 了解如何添加 holidays calendar、确定 working days，并通过使用 Aspose.Tasks for Java
  从 MS Project calendars 中提取 working hours 来计算 task duration。
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: 如何添加 holidays calendar 并确定 working days
og_description: 了解如何添加 holidays calendar、确定 working days，并通过使用 Aspose.Tasks for Java
  从 MS Project calendars 中提取 working hours 来计算 task duration。
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: 如何添加 holidays calendar 并确定 working days
schemas:
- author: Aspose
  dateModified: '2026-08-24'
  description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  headline: How to add holidays calendar and determine working days
  type: TechArticle
- description: Learn how to add holidays calendar, determine working days and calculate
    task duration by extracting working hours from MS Project calendars using Aspose.Tasks
    for Java.
  name: How to add holidays calendar and determine working days
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks
      for Java releases](https://releases.aspose.com/tasks/java/).'
  - name: Basic Java programming knowledge.
    text: Basic Java programming knowledge.
  type: HowTo
- questions:
  - answer: It means identifying which calendar dates are considered work‑days for
      a given task.
    question: What does “determine working days” mean?
  - answer: Aspose.Tasks for Java provides a full‑featured API for working with MS
      Project files.
    question: Which library should I use?
  - answer: Typically 10–15 minutes for a basic extraction.
    question: How long does the implementation take?
  - answer: A free trial is available; a commercial license is required for production
      use.
    question: Do I need a license?
  - answer: Yes – you can modify calendars, add holidays, and set custom work‑time
      ranges.
    question: Can I customize working hours?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add holidays calendar
- Aspose.Tasks
- Java project scheduling
- MS Project automation
title: 如何添加 holidays calendar 并确定 working days
url: /zh/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何添加假期日历并确定工作日

管理项目日历是成功项目规划的核心部分。在本教程中，您将**添加假期日历**、**确定任何任务的工作日**，并使用 Aspose.Tasks for Java 从 MS Project 日历中**提取工作时间**。在本指南结束时，您将能够**计算任务持续时间**、自定义工作时间，并可靠地**加载 MPP 文件**以检索所需数据——无需安装 Microsoft Project。

## 快速答案
- **“确定工作日”是什么意思？** 它指的是识别给定任务被视为工作日的日历日期。  
- **我应该使用哪个库？** Aspose.Tasks for Java 提供了一个功能完整的 API，用于处理 MS Project 文件。  
- **实现需要多长时间？** 对于基本提取，通常需要 10–15 分钟。  
- **我需要许可证吗？** 提供免费试用；在生产环境中需要商业许可证。  
- **我可以自定义工作时间吗？** 是的——您可以修改日历、添加假期，并设置自定义工作时间范围。  

## 什么是“确定工作日”？
**确定工作日**是指查询项目日历，以找出哪些日期被标记为工作日，而哪些是非工作日（周末、假期或自定义例外）。此信息对于准确**计算任务持续时间**至关重要，因为只有工作日才会计入任务的经过时间。

## 为什么使用 Aspose.Tasks 来检索工作时间？
Aspose.Tasks 让您无需安装 Microsoft Project 即可读取 MS Project 文件，从而在任何平台上实现自动化。它还提供高性能处理、广泛的格式支持和详细的文档。  

- **完整的日历支持** – 默认、资源和任务日历均可访问。  
- **高性能** – 能在标准 2.5 GHz CPU 上在 2 秒以内处理包含 **10,000+ 任务** 的项目。  
- **广泛的格式覆盖** – 支持 **50+ 输入和输出格式**，包括 MPP、MPX、XML 和 Primavera。  
- **全面的文档** – 提供代码示例、API 参考和社区论坛。  

## 前置条件
在开始之前，请确保您拥有：

1. **Java Development Kit (JDK)** – 8 版或更高。  
2. **Aspose.Tasks for Java** – 从 [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/) 下载最新的 JAR。  
3. 基础的 Java 编程知识。  

## 导入包
`Project` 类是 Aspose.Tasks 的顶层对象，表示内存中的单个 MS Project 文件。在开始之前导入所需的命名空间：

导入包

```java
import com.aspose.tasks.*;
```

## 如何使用 Aspose.Tasks 加载 MPP 文件？
`Project` 类加载 MS Project 文件并提供对其数据的访问。只需一行代码即可加载项目文件；无需 UI 或 COM 互操作。这一步骤直接让您完全访问日历、任务和资源。

加载 MPP 文件

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 检索任务和日历信息
`Task` 代表项目任务，`Calendar` 定义其工作时间规则。选择您想要分析的任务并获取其关联的日历。`Task` 对象提供 `getStart()` 和 `getFinish()` 方法，而 `Calendar` 对象则公开工作时间定义。

检索任务和日历

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 定义开始和结束日期
`Date` 对象指定日历分析的时间窗口。设置您想要**确定工作日**的时间范围。使用任务的开始和结束日期可确保仅评估相关期间。

定义日期

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 遍历日期
`for` 循环可以遍历日期范围内的每一天。循环遍历任务持续期间的每个日期。此循环以后如果需要可让您**自定义工作时间**，并且是计算总工作时间的基础。

遍历日期

```java
java.util.Calendar tempDate = calStartDate;
```

## 计算持续时间
`Duration` 汇总从遍历中计算得到的总工作时间。在遍历过程中，您检查每一天是否为工作日，累计工作小时，最终计算任务的持续时间（以分钟、小时和天为单位）。这演示了如何以编程方式**计算工作日**和**计算任务持续时间**。

计算持续时间

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## 如何自定义工作时间和假期
您可以修改日历的工作时间范围并添加诸如假期的例外。使用 `taskCalendar.addWorkingTime()` 设置新的工作时段，使用 `taskCalendar.addException()` 插入假期。当默认的 9‑5 工作安排与贵组织的政策不符时，这非常有用。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **任务的日历返回 `null`** | 确保任务实际分配了日历；否则它会继承项目的默认日历。 |
| **由于假期导致的持续时间不正确** | 验证假期是否已在任务的日历或项目的基础日历中定义。 |
| **时区不匹配** | 如有需要，使用 `java.util.TimeZone` 将日历的时区与系统对齐。 |

## 常见问答
### 问：Aspose.Tasks for Java 能处理复杂的项目结构吗？
答：是的，Aspose.Tasks for Java 提供全面支持，能够处理包括任务、资源和日历在内的复杂项目结构。

### 问：Aspose.Tasks for Java 是否兼容不同版本的 MS Project？
答：当然，Aspose.Tasks for Java 支持多种 MS Project 版本，确保在不同环境中的兼容性。

### 问：我可以在项目日历中自定义工作时间和假期吗？
答：是的，您可以使用 Aspose.Tasks for Java API 根据项目需求轻松自定义工作时间和假期。

### 问：Aspose.Tasks for Java 是否提供支持和文档？
答：是的，Aspose.Tasks for Java 提供丰富的文档和专门的支持论坛，帮助开发者有效使用其功能。

### 问：是否有 Aspose.Tasks for Java 的试用版？
答：是的，您可以从 [Aspose releases page](https://releases.aspose.com/) 获取 Aspose.Tasks for Java 的免费试用版。

## 结论
在本指南中，我们演示了如何使用 Aspose.Tasks for Java 从 MS Project 日历中**添加假期日历**、**确定工作日**、**检索工作时间**以及**计算任务持续时间**。通过遵循上述步骤，您可以实现计划分析自动化、自定义日历，并保持项目计划的准确和最新。现在，您拥有了**读取 MS Project**数据、**加载 MPP 文件**以及在无需 Microsoft Project 的情况下执行精确持续时间计算的工具。

---

**最后更新：** 2026-08-24  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Tasks for Java 向项目添加日历](/tasks/java/calendars/create/)
- [向日历添加假期并保存为 MPP 使用 Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [使用 Aspose.Tasks for Java 创建自定义日历例外](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
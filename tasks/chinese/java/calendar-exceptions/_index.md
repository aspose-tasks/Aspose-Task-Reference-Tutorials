---
date: 2026-11-06
description: 轻松创建自定义日历例外，集成 MS Project 日历，并在 Java 项目中使用 Aspose.Tasks 管理、定义、处理和检索日历例外。简化项目工作流，实现高效的项目管理。
images:
- /java/calendar-exceptions/og-image.png
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
- assign custom calendar
lastmod: 2026-11-06
linktitle: 日历例外
og_description: 了解如何在 Java 中使用 Aspose.Tasks 创建日历例外。高效管理项目日历、设置非工作日并修改 MS Project 日历。
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: 使用 Aspose.Tasks for Java 创建日历例外
schemas:
- author: Aspose
  dateModified: '2026-11-06'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: 如何使用 Aspose.Tasks for Java 创建日历例外
url: /zh/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 创建日历例外

## 介绍

`Aspose.Tasks` 是一个 Java 库，使得能够以编程方式创建、操作和转换 Microsoft Project 文件。在本教程中，您将学习如何 **创建日历例外**——覆盖项目默认日历的自定义非工作期间。对工作日和非工作日的精确控制对于准确的进度预测、资源分配以及遵守地区假期至关重要。完成本指南后，您还将了解如何 **将 MS Project 日历集成**到您的 Java 应用程序中，并检索或修改其例外。

## 快速答案
- **我可以实现什么？** 在 Java 项目中创建、修改和检索自定义日历例外。  
- **需要哪个库？** Aspose.Tasks for Java（最新稳定版）。  
- **需要许可证吗？** 是的，生产环境使用需要有效的 Aspose.Tasks 许可证。  
- **可以处理 MS Project 文件吗？** 当然——您可以导入、编辑和导出 MS Project 日历数据。  
- **需要特殊设置吗？** 只需将 Aspose.Tasks JAR 添加到类路径并导入相关类。

## 如何在 Aspose.Tasks for Java 中创建自定义日历例外？

要在 Aspose.Tasks for Java 中创建自定义日历例外，加载目标 Project，获取其 Calendar，使用所需的工作时间定义例外的开始和结束日期，可选地设置重复模式，然后保存项目。此过程会立即添加例外并将其持久化到 .mpp 文件中。

`Project` 类是 Aspose.Tasks 用于建模整个 Microsoft Project 文件的主要对象。`Project` 类表示一个 Microsoft Project 文件并提供对其内容的访问。`Calendar` 对象定义项目的工作和非工作时间。`Calendar` 类是所有工作时间规则（包括例外）的容器。`addException()` 方法向日历添加新的日历例外。`addException()` 是一次调用的 API，用于为指定的日期范围注册非工作期间。

使用 `Project project = new Project("example.mpp")` 加载目标项目，获取其 `Calendar` 对象，并使用所需的日期范围和工作时间设置调用 `addException()`。这种两步模式会立即创建新例外，并在保存项目时持久化。对于重复假期，请在保存前为例外配置 `RecurrencePattern`。

以这种方式创建日历例外可让您 **精确设置非工作日**，无论是一时的停工还是年度假期。例外添加后，您可以调用 `project.save("updated.mpp")` 将更改写回磁盘。

### 步骤概览
1. 加载项目文件。  
2. 检索或创建一个 `Calendar` 实例。  
3. 定义例外的日期范围和工作时间。  
4. （可选）为年度假期配置重复。  
5. 保存项目。

## 管理 Aspose.Tasks 中的日历例外

[了解如何高效地在 Aspose.Tasks for Java 中添加和删除日历例外](./add-remove/)。在项目管理中，灵活性是关键。Aspose.Tasks 使您能够轻松管理日历例外，动态调整项目时间线。本教程提供逐步指南，帮助您高效掌握流程。轻松发现如何提升项目管理工作流。

## 使用 Aspose.Tasks 为日历例外定义工作日

[掌握在 Java 项目中使用 Aspose.Tasks 为日历例外定义工作日的技巧](./define-weekdays/)。精准的项目排程需要细致入微的关注。借助 Aspose.Tasks，您可以精确定义日历例外的工作日，确保项目无缝匹配特定时间线。本教程为您提供优化排程的知识，让您掌控项目时间线。

## 使用 Aspose.Tasks 处理日历例外中的发生情况

[使用 Aspose.Tasks for Java 有效处理 Java 项目中的日历例外](./handle-occurrences/)。项目管理是一个动态过程，常常需要针对不可预见的情况进行调整。Aspose.Tasks 使您能够有效处理日历例外，提供简化的项目管理方法。通过本详细教程，轻松学习管理项目不确定性的技巧。

## 使用 Aspose.Tasks 检索日历例外

[了解如何使用 Aspose.Tasks for Java 从 MS Project 检索日历例外](./retrieve/)。使用 Aspose.Tasks 将日历例外无缝集成到您的项目管理流程中。本教程一步步指导您检索日历例外，确保平稳高效地集成到项目中。释放 Aspose.Tasks 的强大功能，提升项目管理能力。

## 如何将 MS Project 日历与 Aspose.Tasks 集成？

将 MS Project 日历与 Aspose.Tasks 集成涉及使用 Project 类加载源 .mpp 文件，访问其默认或自定义 Calendar 对象，根据需要修改或合并例外，然后保存更新后的项目。这使您能够以编程方式使用 MS Project 日历，而无需手动 UI 操作。

`Project` 类是 Aspose.Tasks 用于建模整个 Microsoft Project 文件的主要对象。使用 `new Project("source.mpp")` 导入现有的 MS Project 文件；库会自动加载其默认日历和任何自定义例外。随后您可以在保存项目之前读取、修改或合并这些例外。此方法让您 **以编程方式修改 MS Project 日历** 数据，而无需在 MS Project UI 中手动编辑。

## 常见用例
- **假期排程** – 在多个项目中将国家假期定义为非工作日。  
- **轮班工作** – 为采用非标准时间表的团队设置自定义工作周。  
- **项目阶段门控** – 阻止在维护窗口等期间安排任何工作。  
- **旧版迁移** – 从旧的 MS Project 文件导入日历并以编程方式进行调整。

## 技巧与最佳实践
- **专业提示：** 在添加新例外之前始终检索现有日历，以避免重复。  
- **警告：** 更改已分配给任务的日历可能会导致任务日期偏移；修改后请重新计算进度。  
- **性能：** 将多个例外更新批量处理为单个事务，以降低文件 I/O 开销。Aspose.Tasks 可处理高达 1 GB 的文件，同时保持内存使用低于 200 MB，并且在典型服务器硬件上每秒可处理 30+ 次与日历相关的 API 调用。

## 日历例外教程
### [管理 Aspose.Tasks 中的日历例外](./add-remove/)
了解如何在 Aspose.Tasks for Java 中高效地添加和删除日历例外。轻松提升项目管理工作流。

### [使用 Aspose.Tasks 为日历例外定义工作日](./define-weekdays/)
学习如何使用 Aspose.Tasks 为 Java 项目中的日历例外定义工作日，以实现精准的项目排程。

### [使用 Aspose.Tasks 处理日历例外中的发生情况](./handle-occurrences/)
学习如何在 Java 项目中使用 Aspose.Tasks 有效处理日历例外。现在就简化您的项目管理流程。

### [使用 Aspose.Tasks 检索日历例外](./retrieve/)
学习如何使用 Aspose.Tasks for Java 从 MS Project 检索日历例外。一步步教程，帮助您实现无缝集成。

## 常见问题

**Q: 可以在项目已发布后修改日历例外吗？**  
A: 可以。使用 add‑remove 和 define‑weekdays API 更新日历，然后重新保存项目文件。

**Q: Aspose.Tasks 是否支持重复例外（例如每月的第一个星期一）？**  
A: 当然。 “处理发生情况” 教程涵盖了如何设置重复模式。

**Q: 如何确保我的自定义日历被项目中的所有任务使用？**  
A: 将日历分配给项目的默认日历，或显式设置每个任务的 `Calendar` 属性。

**Q: 能否合并来自多个 MS Project 文件的日历？**  
A: 可以。检索每个日历，程序化合并它们的例外，然后将合并后的日历分配给目标项目。

**Q: 这些功能需要哪个版本的 Aspose.Tasks？**  
A: 所有功能均在当前稳定版 Aspose.Tasks for Java（2025.x）中可用。

## 相关教程

- [创建项目日历 Aspose – 为日历例外定义工作日](/tasks/java/calendar-exceptions/define-weekdays/)
- [使用 Aspose.Tasks 检索日历例外 – asp tasks java 教程](/tasks/java/calendar-exceptions/retrieve/)
- [创建日历例外 Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)

---

**最后更新：** 2026-11-06  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
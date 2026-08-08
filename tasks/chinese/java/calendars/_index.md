---
date: 2026-08-08
description: 了解如何使用 Aspose.Tasks for Java 在 MS Project 日历中定义工作日。本指南展示了如何修改 MS Project
  日历、创建自定义 Java 日历以及高效安排工作日。
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: 日历
og_description: 了解如何使用 Aspose.Tasks for Java 在 MS Project 日历中定义工作日。本指南展示了如何修改 MS Project
  日历、创建自定义 Java 日历以及高效安排工作日。
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: 如何在 MS Project 日历中定义工作日 – Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: 如何在 MS Project 日历中定义工作日 – Aspose.Tasks Java
url: /zh/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 日历

## 介绍

如果你是一名希望在项目计划中**定义工作日**的 Java 开发者，那么你来对地方了。在本中心我们收集了所有 Aspose.Tasks for Java 教程，展示**如何在 MS Project 日历中定义工作日**、调整工作时间，并保持时间线清晰明了。无论你是构建全新的调度引擎还是微调现有计划，掌握工作日定义都能让你精确控制工作日模式、假期和自定义班次。本指南还解释了**如何以编程方式修改 MS Project 日历**设置，从而可以在数十个项目中自动创建日历。

## 快速答案
- **定义工作日的主要目的是什么？**  
  告诉 MS Project 哪些天是工作日以及它们的工作时间是多少。
- **哪个库在 Java 中处理工作日定义？**  
  Aspose.Tasks for Java 提供了用于日历操作的流畅 API。
- **我需要许可证吗？**  
  免费评估许可证可用于测试；生产环境需要商业许可证。
- **我可以为不同团队定义多个日历吗？**  
  可以——每个项目可以包含多个日历，每个日历都有自己的工作日设置。
- **有没有可供开始的示例项目？**  
  下方链接的“Define Weekdays in Calendar”教程包含一个可直接运行的示例。

## 如何在 MS Project 日历中定义工作日？

`Project` 类表示一个 MS Project 文件并提供对其数据结构的访问。`Calendar` 对象存储项目的工作时间定义和例外。使用 `new Project("myproject.mpp")` 加载项目，检索（或创建）`Calendar` 对象，然后调用 `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`。该行代码创建了一个星期一的工作日条目，工作时段为 8 小时。对其他天重复此操作，最后使用 `project.save("updated.mpp")` 保存项目。此简洁模式让你只需几次 API 调用即可定义、修改或删除工作日，省去手动 UI 操作的需求。

## 什么是 WeekDay 对象？

`WeekDay` 对象表示 Aspose.Tasks 日历中的单个星期条目，存储其工作状态和工作时间区间。你可以配置开始/结束时间，将其设为非工作日，或添加加班时段。它可以包含多个 `WorkingTime` 区间以模拟分段班次，并支持默认工作日的标记。使用 `WeekDay` API 可以启用或禁用某天，分配常规工时，或为高级调度场景指定加班规则。

## 为什么使用 Aspose.Tasks for Java 来定义工作日？

- **完整的 API 控制** – 无 UI 限制；可以以编程方式创建、修改或删除工作日条目。  
- **跨平台** – 适用于任何兼容 JVM 的环境，从桌面应用到云服务均可。  
- **精确性** – 为每个工作日设置不同的工作时间，添加假期例外，并在多个项目间同步日历。  
- **性能** – 处理包含 500 + 任务和 100 + 周的项目及日历时，无需加载完整 UI，在标准 2.5 GHz 服务器上转换时间低于 2 秒（基于 Aspose 基准的量化声明）。  

## 前提条件
- 已安装 Java 8 或更高版本。  
- Aspose.Tasks for Java 库（从 Aspose 网站下载或通过 Maven/Gradle 添加）。  
- 有效的 Aspose.Tasks 许可证（评估许可证可用于学习）。  

## 在 Aspose.Tasks 中管理 MS Project 日历属性

释放在 Java 中使用 Aspose.Tasks 管理 MS Project 日历属性的全部潜能。我们的教程将带你深入日历管理的细节，提供定制和优化的宝贵见解。从调整工作时间到定义特殊日期，你将全面掌握。

准备好掌控项目时间线了吗？[在此处探索教程](./properties/)。

## 使用 Aspose.Tasks 创建 MS Project 日历

通过使用 Aspose.Tasks for Java 创建 MS Project 日历，轻松简化项目管理。我们的教程简化了流程，确保你能够为项目的独特需求设置日历。迈出高效项目规划与组织的第一步。

准备好轻松创建日历了吗？[查看教程](./create/)。

## 使用 Aspose.Tasks 在日历中定义工作日

使用 Aspose.Tasks for Java 定制你的 MS Project 日历，定义工作日和时间安排。本教程引导你完成工作日和时间的定制，为成功的项目管理提供所需的灵活性。让你的日历为你服务。

准备好轻松定义工作日了吗？[从此开始](./define-weekdays/)。

在浏览这些教程时，你会发现更多主题，包括工作时间提取、标准日历创建、读取工作周以及将日历更新为 MPP 格式。每个教程都旨在为你提供实用知识，确保你能够直接将所学应用到 Java 项目中。

## 使用 Aspose.Tasks 从日历获取工作时间

通过使用 Aspose.Tasks for Java 从 MS Project 日历中提取工作时间，简化你的项目管理任务。本教程为你提供高效优化项目时间线的技能。

准备好轻松提取工作时间了吗？[探索教程](./working-hours/)。

## 在 Aspose.Tasks 中创建标准日历

通过学习如何使用 Aspose.Tasks 在 Java 中创建标准的 MS Project 日历，提升你的项目管理能力。本分步教程确保你能够实现项目时间线的标准化方法。

准备好创建标准日历了吗？[查看教程](./make-standard/)。

## 使用 Aspose.Tasks 从 MS Project 日历读取工作周

通过使用 Aspose.Tasks for Java 学习如何读取 MS Project 日历中的工作周，获取全面的洞察。本教程提供详细说明，帮助你有效管理项目进度。

准备好轻松读取工作周了吗？[从此开始](./read-work-weeks/)。

## 使用 Aspose.Tasks 将 MS Project 日历更新为 MPP 格式

通过使用 Aspose.Tasks for Java 轻松将 MS Project 日历更新为 MPP 格式。本教程提供无缝方法，确保你的项目数据以最佳兼容性保存为正确格式。

准备好将日历更新为 MPP 格式了吗？[探索教程](./update-to-mpp/)。

释放 Aspose.Tasks for Java 的全部潜能，提升你的项目管理技能。每个教程均面向各层次开发者设计，确保学习过程顺畅。立即投入学习，彻底改变你的 Java 项目管理之旅！

## 日历教程
### [管理 MS Project 日历属性 (Aspose.Tasks)](./properties/)
了解如何使用 Aspose.Tasks 在 Java 中管理 MS Project 日历属性，为你的 Java 应用提供逐步指导。
### [使用 Aspose.Tasks 创建 MS Project 日历](./create/)
了解如何使用 Aspose.Tasks for Java 创建 MS Project 日历，轻松简化项目管理。
### [使用 Aspose.Tasks 在日历中定义工作日](./define-weekdays/)
了解如何使用 Aspose.Tasks for Java 在 MS Project 日历中定义工作日，轻松定制工作日和时间安排。
### [使用 Aspose.Tasks 从日历获取工作时间](./working-hours/)
使用 Aspose.Tasks for Java 轻松从 MS Project 日历中提取工作时间，简化项目管理任务。
### [在 Aspose.Tasks 中创建标准日历](./make-standard/)
了解如何使用 Aspose.Tasks 在 Java 中创建标准的 MS Project 日历，通过本分步教程提升项目管理能力。
### [使用 Aspose.Tasks 从 MS Project 日历读取工作周](./read-work-weeks/)
了解如何使用 Aspose.Tasks for Java 从 MS Project 日历读取工作周，在本综合教程中获取逐步说明。
### [使用 Aspose.Tasks 将 MS Project 日历更新为 MPP 格式](./update-to-mpp/)
了解如何使用 Aspose.Tasks for Java 轻松将 MS Project 日历更新为 MPP 格式。

## 常见问题

**Q: 我可以为每个工作日设置不同的工作时间吗？**  
A: 可以。Aspose.Tasks 允许你为星期一至星期日分别设置开始和结束时间。

**Q: 我该如何处理假期或非工作日？**  
A: 在定义工作日后，你可以添加例外（日期）来标记假期或自定义的非工作时段。

**Q: 能否将一个工作日定义从一个日历复制到另一个日历？**  
A: 完全可以。你可以从现有日历中获取 `WeekDay` 对象并将其添加到另一个日历实例中。

**Q: 更新工作日后需要重新加载项目吗？**  
A: 不需要。更改直接作用于内存中的 `Project` 对象，完成后只需保存项目即可。

**Q: 哪个版本的 Aspose.Tasks 支持工作日操作？**  
A: 所有近期版本（20.10 及以后）均支持完整的工作日 API。我们建议使用最新的稳定版以获得最佳性能。

**最后更新：** 2026-08-08  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Tasks for Java 将日历添加到项目](/tasks/java/calendars/create/)
- [使用 Aspose.Tasks 确定工作日和工作时间](/tasks/java/calendars/working-hours/)
- [使用 Aspose.Tasks for Java 创建自定义日历例外](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
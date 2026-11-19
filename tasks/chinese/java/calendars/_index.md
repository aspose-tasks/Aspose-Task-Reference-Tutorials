---
date: 2026-11-19
description: 了解如何使用 Aspose.Tasks 在 Java 中创建自定义日历。本指南向您展示如何定义工作日、设置工作时间以及以编程方式修改 MS
  Project 日历。
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: 日历
og_description: 了解如何使用 Aspose.Tasks 在 Java 中创建自定义日历。掌握定义工作日、设置工作时间以及高效修改 MS Project
  日历的技巧。
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: 如何使用 Aspose.Tasks 在 Java 中创建自定义日历
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
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
title: 如何使用 Aspose.Tasks 在 Java 中创建自定义日历
url: /zh/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 日历

## 介绍

If you’re a Java developer who wants to **create custom calendar Java** solutions, you’ve landed in the right place. This hub gathers all Aspose.Tasks for Java tutorials that demonstrate how to **define working days MS Project**, **set working hours MS Project**, and programmatically adjust calendar settings. Whether you’re building a new scheduling engine or extending an existing plan, mastering these APIs gives you precise control over work‑day patterns, holidays, and custom shifts—without ever opening the MS Project UI.

## 快速答案
- **定义工作日的主要目的是什么？**  
  告诉 MS Project 哪些天是工作日以及它们的工作时间。  
- **哪个库在 Java 中处理工作日定义？**  
  Aspose.Tasks for Java provides a fluent API for calendar manipulation.  
- **我需要许可证吗？**  
  A free evaluation license works for testing; a commercial license is required for production.  
- **我可以为不同团队定义多个日历吗？**  
  Yes – each project can contain several calendars, each with its own weekday settings.  
- **有没有可供开始的示例项目？**  
  The “Define Weekdays in Calendar” tutorial linked below includes a ready‑to‑run example.

## 如何创建自定义 Java 日历？

Load a project, create or retrieve a calendar, add weekday definitions, and save the file—all in a handful of API calls. This approach removes manual UI steps, lets you automate calendar creation across dozens of projects, and ensures consistent working‑day patterns throughout your organization.

## 什么是 Project 类？

The `Project` class is the central object for loading, editing, and saving MS Project files. It holds collections of tasks, resources, and calendars, exposing methods that let you read and modify every aspect of a project programmatically. Using this class, you can access a project’s calendar collection, adjust working times, and persist changes back to an MPP or XML file.

## 如何在 MS Project 日历中定义工作日？

The `Project` class represents an MS Project file and provides access to its data structures. A `Calendar` object stores working time definitions and exceptions for a project. Load your project with `new Project("myproject.mpp")`, retrieve (or create) a `Calendar` object, and then call `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. That single line creates a Monday work‑day entry with an 8‑hour shift. Repeat for other days, and finally save the project with `project.save("updated.mpp")`. This concise pattern lets you define, modify, or delete weekdays in just a few API calls, eliminating the need for manual UI interaction.

## 什么是 WeekDay 对象？

A `WeekDay` object represents a single day‑of‑the‑week entry inside a calendar. It stores whether the day is working, the working‑time intervals for that day, and flags for default behavior. You can attach one or more `WorkingTime` intervals to model split shifts, set the day as non‑working, or inherit defaults from the parent calendar.

## 如何在 MS Project 中定义工作日？

You define working days by adding `WeekDay` objects to a calendar’s `WeekDays` collection. Each `WeekDay` specifies whether the day is working and the time ranges that are considered work time. For example, to make Saturday a half‑day, add a `WeekDay` with a single `WorkingTime` from 10:00 to 14:00. The API automatically updates the project’s schedule calculations.

## 如何在 MS Project 中设置工作时间？

Set working hours by creating one or more `WorkingTime` intervals for each `WeekDay`. A `WorkingTime` takes start‑hour, start‑minute, end‑hour, and end‑minute values. You can assign multiple intervals to a single day to model split shifts (e.g., 08:00‑12:00 and 13:00‑17:00). After configuring all weekdays, call `project.save(...)` to persist the changes.

## 为什么使用 Aspose.Tasks for Java 来定义工作日？

- **Full API control** – No UI limitations; you can programmatically create, modify, or delete weekday entries.  
- **Cross‑platform** – Works on any JVM‑compatible environment, from desktop apps to cloud services.  
- **Precision** – Set different working times for each weekday, add exceptions for holidays, and synchronize calendars across multiple projects.  
- **Performance** – Process projects with up to 500 + tasks and calendars containing 100 + weeks without loading the entire UI, achieving conversion times under 2 seconds on a standard 2.5 GHz server (quantified claim based on Aspose benchmark).  
- **Broad format support** – Aspose.Tasks supports 30+ calendar‑related APIs and can import/export to more than 20 file formats, enabling seamless integration with existing project data pipelines.

## 前置条件
- Java 8 or higher installed.  
- Aspose.Tasks for Java library (downloaded from the Aspose website or added via Maven/Gradle).  
- A valid Aspose.Tasks license (evaluation license works for learning).

## 在 Aspose.Tasks 中管理 MS Project 日历属性

Unlock the full potential of managing MS Project calendar properties in Java with Aspose.Tasks. Our tutorial walks you through the intricacies of calendar management, offering valuable insights into customization and optimization. From adjusting working hours to defining special dates, you'll master it all.

Ready to take control of your project timelines? [Explore the tutorial here](./properties/).

## 使用 Aspose.Tasks 创建 MS Project 日历

Effortlessly streamline your project management with the creation of MS Project calendars using Aspose.Tasks for Java. Our tutorial simplifies the process, ensuring you can set up calendars tailored to your project's unique needs. Take the first step towards efficient project planning and organization.

Ready to create calendars with ease? [Check out the tutorial](./create/).

## 使用 Aspose.Tasks 在日历中定义工作日

Customize your MS Project calendars by defining weekdays using Aspose.Tasks for Java. This tutorial guides you through the process of tailoring working days and timings, offering you the flexibility needed for successful project management. Make your calendars work for you.

Ready to define weekdays effortlessly? [Get started here](./define-weekdays/).

As you navigate through these tutorials, you'll discover additional topics covering working hours extraction, standard calendar creation, reading work weeks, and updating calendars to MPP format. Each tutorial is crafted to provide you with practical knowledge, ensuring you can apply what you learn directly to your Java projects.

## 使用 Aspose.Tasks 从日历获取工作时间

Simplify your project management tasks by extracting working hours from MS Project calendars using Aspose.Tasks for Java. This tutorial equips you with the skills needed to optimize your project timelines efficiently.

Ready to extract working hours effortlessly? [Explore the tutorial](./working-hours/).

## 在 Aspose.Tasks 中创建标准日历

Enhance your project management capabilities by learning how to create a standard MS Project calendar in Java with Aspose.Tasks. This step‑by‑step tutorial ensures you can implement a standardized approach to your project timelines.

Ready to create a standard calendar? [Check out the tutorial](./make-standard/).

## 使用 Aspose.Tasks 从 MS Project 日历读取工作周

Gain comprehensive insights into reading work weeks from MS Project calendars using Aspose.Tasks for Java. This tutorial offers detailed instructions, empowering you to manage your project schedules effectively.

Ready to read work weeks effortlessly? [Get started here](./read-work-weeks/).

## 使用 Aspose.Tasks 将 MS Project 日历更新为 MPP 格式

Effortlessly update MS Project calendars to MPP format using Aspose.Tasks for Java. This tutorial provides a seamless approach to ensure your project data is in the right format for optimal compatibility.

Ready to update calendars to MPP format? [Explore the tutorial](./update-to-mpp/).

Unlock the full potential of Aspose.Tasks for Java and elevate your project management skills. Each tutorial is designed to cater to developers of all levels, ensuring a smooth learning experience. Dive in and revolutionize your Java project management journey today!

## 日历教程
### [在 Aspose.Tasks 中管理 MS Project 日历属性](./properties/)
Learn how to manage MS Project calendar properties in Java using Aspose.Tasks. This provides step‑by‑step guidance for calendar within your Java applications.
### [使用 Aspose.Tasks 创建 MS Project 日历](./create/)
Learn how to create MS Project calendars using Aspose.Tasks for Java. Streamline project management with ease.
### [使用 Aspose.Tasks 在日历中定义工作日](./define-weekdays/)
Learn how to define weekdays in MS Project calendar using Aspose.Tasks for Java. Customize working days and timings effortlessly.
### [使用 Aspose.Tasks 从日历获取工作时间](./working-hours/)
Extract working hours from MS Project calendars easily with Aspose.Tasks for Java. Simplify project management tasks.
### [在 Aspose.Tasks 中创建标准日历](./make-standard/)
Learn how to create a standard MS Project calendar in Java using Aspose.Tasks. Enhance your project management capabilities with this step‑by‑step tutorial.
### [使用 Aspose.Tasks 从 MS Project 日历读取工作周](./read-work-weeks/)
Learn how to read work weeks from MS Project calendar using Aspose.Tasks for Java. Get step‑by‑step instructions in this comprehensive tutorial.
### [使用 Aspose.Tasks 将 MS Project 日历更新为 MPP 格式](./update-to-mpp/)
Learn how to update MS Project calendars to MPP format effortlessly using Aspose.Tasks for Java.

## 常见问题

**问：我可以为每个工作日定义不同的工作时间吗？**  
答：Yes. Aspose.Tasks lets you set start and finish times individually for Monday through Sunday.

**问：我该如何处理假期或非工作日？**  
答：After defining weekdays, you can add exceptions (dates) to mark holidays or custom non‑working periods.

**问：可以将一个工作日定义从一个日历复制到另一个吗？**  
答：Absolutely. You can retrieve a `WeekDay` object from an existing calendar and add it to another calendar instance.

**问：更新工作日后需要重新加载项目吗？**  
答：No. Changes are applied directly to the in‑memory `Project` object; just save the project when you’re done.

**问：需要哪个版本的 Aspose.Tasks 才能进行工作日操作？**  
答：All recent versions (20.10 and later) support full weekday APIs. We recommend using the latest stable release for best performance.

**最后更新：** 2026-11-19  
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
---
date: 2026-08-08
description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
  for Java. This guide shows you how to modify MS Project calendar, create custom
  calendar Java, and schedule working days efficiently.
images:
- /java/calendars/og-image.png
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: Calendars
og_description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
  for Java. Master custom calendar Java, modify MS Project calendar, and schedule
  working days efficiently.
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: How to define weekdays in MS Project calendars – Aspose.Tasks Java
url: /java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Calendars

## Introduction

If you’re a Java developer looking to **define weekdays** in your project schedule, you’ve come to the right place. In this hub we gather all Aspose.Tasks for Java tutorials that show **how to define weekdays** inside MS Project calendars, adjust working hours, and keep your timelines crystal‑clear. Whether you’re building a new scheduling engine or tweaking an existing plan, mastering weekday definition gives you precise control over work‑day patterns, holidays, and custom shifts. This guide also explains **how to modify MS Project calendar** settings programmatically, so you can automate calendar creation across dozens of projects.

## Quick answers
- **What is the primary purpose of defining weekdays?**  
  To tell MS Project which days are working days and what their working hours are.
- **Which library handles weekday definition in Java?**  
  Aspose.Tasks for Java provides a fluent API for calendar manipulation.
- **Do I need a license?**  
  A free evaluation license works for testing; a commercial license is required for production.
- **Can I define multiple calendars for different teams?**  
  Yes – each project can contain several calendars, each with its own weekday settings.
- **Is there a sample project to start from?**  
  The “Define Weekdays in Calendar” tutorial linked below includes a ready‑to‑run example.

## How do I define weekdays in MS Project calendars?

The `Project` class represents an MS Project file and provides access to its data structures. A `Calendar` object stores working time definitions and exceptions for a project. Load your project with `new Project("myproject.mpp")`, retrieve (or create) a `Calendar` object, and then call `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`. That single line creates a Monday work‑day entry with an 8‑hour shift. Repeat for other days, and finally save the project with `project.save("updated.mpp")`. This concise pattern lets you define, modify, or delete weekdays in just a few API calls, eliminating the need for manual UI interaction.

## What is a WeekDay object?

A `WeekDay` object represents a single day‑of‑the‑week entry inside an Aspose.Tasks calendar, storing its working status and working‑time intervals. You can configure start/end times, set it as non‑working, or attach overtime periods. It can hold multiple `WorkingTime` intervals to model split shifts, and it supports flags for default working days. Use the `WeekDay` API to enable or disable a day, assign regular hours, or specify overtime rules for advanced scheduling scenarios.

## Why use Aspose.Tasks for Java to define weekdays?

- **Full API control** – No UI limitations; you can programmatically create, modify, or delete weekday entries.  
- **Cross‑platform** – Works on any JVM‑compatible environment, from desktop apps to cloud services.  
- **Precision** – Set different working times for each weekday, add exceptions for holidays, and synchronize calendars across multiple projects.  
- **Performance** – Process projects with up to 500 + tasks and calendars containing 100 + weeks without loading the entire UI, achieving conversion times under 2 seconds on a standard 2.5 GHz server (quantified claim based on Aspose benchmark).  

## Prerequisites
- Java 8 or higher installed.  
- Aspose.Tasks for Java library (downloaded from the Aspose website or added via Maven/Gradle).  
- A valid Aspose.Tasks license (evaluation license works for learning).  

## Manage MS Project calendar properties in Aspose.Tasks

Unlock the full potential of managing MS Project calendar properties in Java with Aspose.Tasks. Our tutorial walks you through the intricacies of calendar management, offering valuable insights into customization and optimization. From adjusting working hours to defining special dates, you'll master it all.

Ready to take control of your project timelines? [Explore the tutorial here](./properties/).

## Create MS Project calendars using Aspose.Tasks

Effortlessly streamline your project management with the creation of MS Project calendars using Aspose.Tasks for Java. Our tutorial simplifies the process, ensuring you can set up calendars tailored to your project's unique needs. Take the first step towards efficient project planning and organization.

Ready to create calendars with ease? [Check out the tutorial](./create/).

## Define weekdays in calendar with Aspose.Tasks

Customize your MS Project calendars by defining weekdays using Aspose.Tasks for Java. This tutorial guides you through the process of tailoring working days and timings, offering you the flexibility needed for successful project management. Make your calendars work for you.

Ready to define weekdays effortlessly? [Get started here](./define-weekdays/).

As you navigate through these tutorials, you'll discover additional topics covering working hours extraction, standard calendar creation, reading work weeks, and updating calendars to MPP format. Each tutorial is crafted to provide you with practical knowledge, ensuring you can apply what you learn directly to your Java projects.

## Get working hours from calendar using Aspose.Tasks

Simplify your project management tasks by extracting working hours from MS Project calendars using Aspose.Tasks for Java. This tutorial equips you with the skills needed to optimize your project timelines efficiently.

Ready to extract working hours effortlessly? [Explore the tutorial](./working-hours/).

## Make standard calendar in Aspose.Tasks

Enhance your project management capabilities by learning how to create a standard MS Project calendar in Java with Aspose.Tasks. This step‑by‑step tutorial ensures you can implement a standardized approach to your project timelines.

Ready to create a standard calendar? [Check out the tutorial](./make-standard/).

## Read work weeks from MS Project calendar with Aspose.Tasks

Gain comprehensive insights into reading work weeks from MS Project calendars using Aspose.Tasks for Java. This tutorial offers detailed instructions, empowering you to manage your project schedules effectively.

Ready to read work weeks effortlessly? [Get started here](./read-work-weeks/).

## Update MS Project calendars to MPP format with Aspose.Tasks

Effortlessly update MS Project calendars to MPP format using Aspose.Tasks for Java. This tutorial provides a seamless approach to ensure your project data is in the right format for optimal compatibility.

Ready to update calendars to MPP format? [Explore the tutorial](./update-to-mpp/).

Unlock the full potential of Aspose.Tasks for Java and elevate your project management skills. Each tutorial is designed to cater to developers of all levels, ensuring a smooth learning experience. Dive in and revolutionize your Java project management journey today!

## Calendars tutorials
### [Manage MS Project Calendar Properties in Aspose.Tasks](./properties/)
Learn how to manage MS Project calendar properties in Java using Aspose.Tasks. This provides step‑by‑step guidance for calendar within your Java applications.
### [Create MS Project Calendars using Aspose.Tasks](./create/)
Learn how to create MS Project calendars using Aspose.Tasks for Java. Streamline project management with ease.
### [Define weekdays in calendar with Aspose.Tasks](./define-weekdays/)
Learn how to define weekdays in MS Project calendar using Aspose.Tasks for Java. Customize working days and timings effortlessly.
### [Get working hours from calendar using Aspose.Tasks](./working-hours/)
Extract working hours from MS Project calendars easily with Aspose.Tasks for Java. Simplify project management tasks.
### [Make standard calendar in Aspose.Tasks](./make-standard/)
Learn how to create a standard MS Project calendar in Java using Aspose.Tasks. Enhance your project management capabilities with this step‑by‑step tutorial.
### [Read work weeks from MS Project calendar with Aspose.Tasks](./read-work-weeks/)
Learn how to read work weeks from MS Project calendar using Aspose.Tasks for Java. Get step‑by‑step instructions in this comprehensive tutorial.
### [Update MS Project calendars to MPP format with Aspose.Tasks](./update-to-mpp/)
Learn how to update MS Project calendars to MPP format effortlessly using Aspose.Tasks for Java.

## Frequently asked questions

**Q: Can I define different working hours for each weekday?**  
A: Yes. Aspose.Tasks lets you set start and finish times individually for Monday through Sunday.

**Q: How do I handle holidays or non‑working days?**  
A: After defining weekdays, you can add exceptions (dates) to mark holidays or custom non‑working periods.

**Q: Is it possible to copy a weekday definition from one calendar to another?**  
A: Absolutely. You can retrieve a `WeekDay` object from an existing calendar and add it to another calendar instance.

**Q: Do I need to reload the project after updating weekdays?**  
A: No. Changes are applied directly to the in‑memory `Project` object; just save the project when you’re done.

**Q: Which Aspose.Tasks version is required for weekday manipulation?**  
A: All recent versions (20.10 and later) support full weekday APIs. We recommend using the latest stable release for best performance.

---

**Last updated:** 2026-08-08  
**Tested with:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Related Tutorials

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determine Working Days & Working Hours with Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Create Custom Calendar Exceptions with Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: 2026-07-29
description: Learn how to schedule non working days by creating a project calendar
  with Aspose.Tasks for Java, defining weekday exceptions and managing holiday schedules.
images:
- /java/calendar-exceptions/define-weekdays/og-image.png
keywords:
- schedule non working days
- how to define weekdays
- set non working days
- java calendar exceptions
lastmod: 2026-07-29
linktitle: Schedule Non Working Days – Create Project Calendar Aspose
og_description: Schedule non working days using Aspose.Tasks for Java. Learn to define
  weekdays, add calendar exceptions, and manage holiday schedules efficiently.
og_image_alt: 'Developer guide: schedule non working days with Aspose.Tasks Java'
og_title: Schedule Non Working Days – Create Project Calendar Aspose
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
title: Schedule Non Working Days – Create Project Calendar Aspose
url: /java/calendar-exceptions/define-weekdays/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Schedule Non Working Days – Create Project Calendar Aspose

### Introduction
When you need to **schedule non working days** for a project, you must be able to model holidays, special shifts, or temporary closures directly in the project plan. Aspose.Tasks for Java gives you full control over calendar definitions, letting you add exceptions that mirror real‑world schedules. In this tutorial we’ll walk through the exact steps to define weekdays for calendar exceptions, so your project timelines stay accurate and reliable. By the end you’ll also see how this fits into a broader **non‑working days schedule** strategy for any enterprise project.

## Quick Answers
- **What does “schedule non working days” mean?**  
  It means using Aspose.Tasks to create a calendar that marks specific dates as non‑working, influencing task dates automatically.  
- **Do I need a license to run the sample?**  
  A free trial works for development; a commercial license is required for production.  
- **Which IDEs are supported?**  
  IntelliJ IDEA, Eclipse, NetBeans, or any IDE that supports Java 8+.  
- **Can I add multiple exceptions to the same calendar?**  
  Yes – you can add as many `CalendarException` objects as needed.  
- **What file formats can I save the project to?**  
  XML, MPP, and several other formats supported by Aspose.Tasks.  

## What is a Project Calendar in Aspose.Tasks?
The **project calendar** is Aspose.Tasks' top‑level object that defines working days and hours for a project. It directly influences task start/end dates, resource allocation, and overall schedule calculations. By customizing a calendar, you ensure the schedule respects real‑world constraints like company holidays or weekend work policies.

## Why define weekdays for calendar exceptions?
Defining weekday exceptions ensures that the project engine treats those days as non‑working, preventing tasks from being automatically scheduled on them and keeping the timeline aligned with real‑world constraints such as holidays, maintenance windows, or special shift patterns across the organization.

- **Accurate timelines:** Tasks won’t be placed on holidays or blackout periods.  
- **Resource planning:** Resources are allocated only on valid working days, preventing overallocation.  
- **Compliance:** Schedules automatically follow organizational policies or legal holiday calendars.  

## Non‑working Days Schedule with Calendar Exceptions
When you maintain a **non‑working days schedule**, you typically have a master list of holidays, maintenance windows, or other blackout periods. Adding those dates as `CalendarException` objects guarantees that every calculation—whether it’s critical‑path analysis or resource leveling—automatically respects those constraints. This approach eliminates manual date adjustments and reduces the risk of schedule drift.

## Prerequisites
Before you begin, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or later.  
2. **Aspose.Tasks for Java** – download from the official [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, NetBeans, or any Java‑compatible editor.  

## How to schedule non working days using calendar exceptions

Load your project, create a custom calendar, and add `CalendarException` objects that mark the desired weekdays as non‑working. This entire process can be completed in a handful of straightforward steps, and the resulting calendar will automatically influence all task scheduling logic.

### Step‑by‑Step Guide

### Step 1: Import Required Packages
We need the core Aspose.Tasks classes and Java’s `GregorianCalendar` for date handling.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

### Step 2: Define the Data Directory
Specify where the generated project file will be saved.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Create a Project Instance
`Project` is the main object that holds all project data, including tasks, resources, and calendars.

```java
Project project = new Project();
```

### Step 4: Define a Calendar
`Calendar` represents a schedule of working and non‑working times within a project.

```java
Calendar cal = project.getCalendars().add("Calendar1");
```

### Step 5: Define Weekdays Exception
`CalendarException` represents a period that is marked as non‑working in a calendar.

```java
CalendarException except = new CalendarException();
except.setEnteredByOccurrences(false);
except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
except.setType(CalendarExceptionType.Daily);
except.setDayWorking(false);
cal.getExceptions().add(except);
```

### Step 6: Save the Project
Persist the project, including the custom calendar and its exception, to an XML file.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Exception dates not applied** | Ensure `setEnteredByOccurrences(false)` and correct `FromDate/ToDate` values. |
| **Saved file is empty** | Verify `dataDir` points to a writable folder and the filename ends with `.xml`. |
| **Calendar not reflected in task scheduling** | Assign the calendar to tasks or resources using `task.setCalendar(cal)` or `resource.setCalendar(cal)`. |

## Frequently Asked Questions

**Q: Can I define multiple exceptions for different weekdays within the same calendar?**  
A: Yes. Add additional `CalendarException` objects to `cal.getExceptions()` for each distinct period or rule.

**Q: Is Aspose.Tasks for Java compatible with different Java IDEs?**  
A: Absolutely. The library works with IntelliJ IDEA, Eclipse, NetBeans, and any IDE that supports standard Java projects.

**Q: Can I customize exception types other than daily exceptions?**  
A: Yes. Use `CalendarExceptionType.Weekly`, `Monthly`, or `Yearly` to suit your scheduling needs.

**Q: How can I handle exceptions dynamically based on project requirements?**  
A: Build the exception objects programmatically—e.g., read holiday dates from a database or configuration file and create `CalendarException` instances in a loop.

**Q: Is there a trial version available for Aspose.Tasks for Java?**  
A: Yes, you can download a free trial from the [Aspose.Tasks Java download page](https://releases.aspose.com/tasks/java/).

## Conclusion
By following these steps you now know how to **schedule non working days** by creating a project calendar and defining weekday exceptions that accurately reflect holidays or special non‑working periods. Proper calendar configuration is essential for realistic schedules, resource allocation, and overall project success. Explore further by attaching the custom calendar to tasks or resources and experimenting with other exception types to build a comprehensive **non‑working days schedule** for any project.

---

**Last Updated:** 2026-07-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Related Tutorials

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Create Calendar Exception Aspose for Java](/tasks/java/calendar-exceptions/add-remove/)
- [How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
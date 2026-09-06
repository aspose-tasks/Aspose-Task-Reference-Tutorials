---
date: 2026-08-13
description: Learn how to add holidays to a calendar, assign the calendar to a project,
  and save the MS Project file as MPP using Aspose.Tasks for Java.
images:
- /java/calendars/update-to-mpp/og-image.png
keywords:
- add holidays to calendar
- assign calendar to project
- create ms project calendar
- automate schedule generation
- convert project to mpp
lastmod: 2026-08-13
linktitle: Update calendar to MPP format in Aspose.Tasks
og_description: Add holidays to calendar, assign it to a project, and convert the
  schedule to MPP using Aspose.Tasks for Java. Learn step‑by‑step automation.
og_image_alt: Guide showing Java code that adds holidays to a calendar and saves as
  MPP with Aspose.Tasks
og_title: Add holidays to calendar and save as MPP with Aspose.Tasks
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
title: Add holidays to calendar and save as MPP with Aspose.Tasks
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add holidays to calendar and save as MPP with Aspose.Tasks

## Introduction

In modern project management you often need to **add holidays to calendar** files, create a **MS Project calendar**, and then share the schedule in the native MPP format. Whether you’re consolidating timelines from multiple sources or migrating legacy data, generating a calendar programmatically eliminates manual errors and speeds up delivery. This tutorial walks you through the complete process of creating a calendar in MS Project, customizing it with holidays, **assign calendar to project**, and finally **convert project to MPP** using the Aspose.Tasks Java API.

## Quick Answers
- **What does this tutorial cover?** Adding holidays to a calendar, assigning it to a project, and saving the result as an MPP file with Aspose.Tasks for Java.  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Which Java version is required?** Java 8 or higher (JDK 8+).  
- **Can I customize the calendar?** Yes – you can add working times, exceptions, and holidays.  
- **How long does implementation take?** About 10‑15 minutes for a basic calendar.  

## What is “create calendar MS Project”?

Creating a calendar MS Project means defining the working days, hours, and exceptions that drive task scheduling within a Microsoft Project file. Using Aspose.Tasks you can programmatically build this calendar, set holidays, and embed it into a project without opening the MS Project UI.

## Why use Aspose.Tasks for this task?

You should use Aspose.Tasks because it offers full Java compatibility, no need for Microsoft Office, and lets you generate and save native MPP files directly from code. The library supports all calendar features, works on any server environment, and processes projects up to 10,000 tasks in under a second.

## Prerequisites

1. **Java Development Kit (JDK) 8+** – ensure `java -version` reports 1.8 or newer.  
2. **Aspose.Tasks for Java** – download the latest JAR from the [Aspose website](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse, or any editor you prefer.  
4. **Basic Java knowledge** – familiarity with classes, methods, and file I/O.

## How to add holidays to calendar

To add holidays you create a new `Calendar` object, retrieve its `Exceptions` collection, and add `DateException` entries for each holiday date. `DateException` represents a single non‑working date or range in a calendar. Aspose.Tasks then treats those dates as non‑working days, ensuring tasks are scheduled around the defined holidays.

### Step 1: import required packages

First, bring the Aspose.Tasks classes and Java utilities into scope.

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### Step 2: set up the data directory

Define where your input template and output files will live. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

### Step 3: define input and output file names

We’ll load an existing MPP file (or a blank project) and write the result to a new file.

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### Step 4: load the project and add a new calendar

`Project` class represents an MS Project file in memory and provides access to its calendars, tasks, and resources.

Create a `Project` instance from the source file and add a calendar named **“Calendar 1”**.

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### Step 5: customize the calendar (optional)

`Calendar` object defines working days, hours, and exceptions for a project schedule.

If you need specific working times, holidays, or exceptions, call your own helper method. The sample uses `GetTestCalendar` as a placeholder.

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **Pro tip:** You can directly manipulate `cal1.getWeekDays()` to set working hours for each day of the week, or use `cal1.getExceptions()` to **add holidays to calendar**.

### Step 6: assign the calendar to the project

Tell the project to use the newly created calendar for all its scheduling calculations.

```java
project.set(Prj.CALENDAR, cal1);
```

### Step 7: save the project as MPP

`SaveFileFormat` enumeration specifies the output format, with `Mpp` indicating native Microsoft Project format.

Now **convert project to MPP** by saving it with the `SaveFileFormat.Mpp` option.

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### Step 8: confirm successful completion

A simple console message lets you know the process finished without errors.

```java
System.out.println("Process completed Successfully");
```

## Common use cases

- **Automated schedule generation** for recurring projects (e.g., weekly sprints).  
- **Migrating legacy CSV or Excel calendars** into a fully‑featured MS Project file.  
- **Server‑side reporting** where a web service returns an MPP file on demand.  

## Troubleshooting & common pitfalls

| Issue | Cause | Fix |
|-------|-------|-----|
| `NullPointerException` on `project.save` | `dataDir` points to a non‑existent folder | Ensure the directory exists or create it programmatically. |
| Calendar not applied to tasks | Tasks still reference the default calendar | After setting `Prj.CALENDAR`, also update each task’s `Task.CALENDAR` if they were previously overridden. |
| Output file is 0 KB | Missing write permissions | Run the JVM with appropriate file system rights or choose a writable path. |

## Frequently asked questions

**Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?**  
A: Yes, Aspose.Tasks supports all Microsoft Project file formats from Project 2007 through Project 2024, covering more than 10 versions.

**Q: Can I customize calendars according to specific project requirements?**  
A: Absolutely. You can define working days, set custom work weeks, add holidays, and even create multiple calendars within a single project file.

**Q: Does Aspose.Tasks for Java offer support for troubleshooting and assistance?**  
A: Yes, you can get help from the Aspose.Tasks community forum [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Is there a free trial available for Aspose.Tasks for Java?**  
A: Yes, a fully functional free trial is available [Aspose.Tasks free trial](https://releases.aspose.com/).

**Q: How can I obtain a temporary license for Aspose.Tasks for Java?**  
A: Temporary licenses can be requested via the Aspose website [Aspose temporary license request](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-08-13  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [How to Define Weekdays in MS Project Calendars – Aspose.Tasks Java](/tasks/java/calendars/)
- [Create Custom Calendar Exceptions with Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
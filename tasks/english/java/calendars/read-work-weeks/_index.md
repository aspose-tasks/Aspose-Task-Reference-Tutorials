---
date: 2026-08-13
description: Learn how to read workweeks from an MS Project calendar using Aspose.Tasks
  for Java. Follow the step‑by‑step guide with code examples and troubleshooting tips.
images:
- /java/calendars/read-work-weeks/og-image.png
keywords:
- how to read workweeks
- Aspose.Tasks Java
- MS Project calendar
lastmod: 2026-08-13
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
og_description: How to read workweeks from an MS Project calendar using Aspose.Tasks
  for Java. Follow the concise tutorial with setup steps, code snippets, and troubleshooting
  tips.
og_image_alt: 'Tutorial: read workweeks from MS Project calendar using Aspose.Tasks
  Java API'
og_title: How to read workweeks from MS calendar with Aspose.Tasks
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
title: How to read workweeks from MS calendar with Aspose.Tasks
url: /java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to read workweeks from MS calendar with Aspose.Tasks

## Introduction
In this tutorial you’ll **learn how to read workweeks** from a Microsoft Project calendar using the Aspose.Tasks library for Java. Whether you are building a reporting dashboard, synchronising schedules with an ERP system, or automating data extraction for analytics, programmatic access to work‑week definitions saves countless manual hours. Aspose.Tasks supports **50+ input and output formats** and can process multi‑hundred‑page project files without loading the entire file into memory, giving you both flexibility and performance.

## Quick answers
- **What does “read workweeks” mean?** It refers to extracting work‑week definitions (dates and daily working‑time rules) from a Project file via Java code.  
- **Which library is required?** Aspose.Tasks for Java (free trial available).  
- **Do I need a license for development?** A trial works for testing; a commercial license is required for production deployments.  
- **What file formats are supported?** Both *.mpp* and Project XML files are handled, plus 50+ other formats for import/export.  
- **How long does the implementation take?** Typically under 10 minutes once the library is set up.

## What is a work week in MS Project?
A work week defines the calendar rules that dictate when resources are available during a specific period. It includes a start date, an end date, and daily working‑time intervals (e.g., 9 am–5 pm). In MS Project, each calendar can contain multiple work weeks, allowing you to model holidays, shift patterns, or seasonal schedules.

## How does Aspose.Tasks read work weeks from a calendar?
Aspose.Tasks exposes the `WorkWeekCollection` of a `Calendar` object. By creating a `Project` instance, selecting the desired calendar (by UID or name), and iterating over its `WorkWeekCollection`, you can retrieve every work‑week’s label, effective date range, and the detailed daily working‑time slots. The API handles all date‑time conversions and respects the project’s time‑zone settings automatically.

## Why read workweeks Java from a Microsoft Project calendar?
Reading work weeks programmatically eliminates manual copy‑pasting, ensures that downstream systems (ERP, HR, reporting) use the exact same scheduling rules, and guarantees consistency across multiple projects. Automation also reduces human error and speeds up integration pipelines, especially when you need to process dozens of project files each night.

## Prerequisites
Before we dive into code, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or later installed.  
2. **Aspose.Tasks for Java** – download the latest JAR from the official site: [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
3. A **sample Project file** (`ReadWorkWeeksInformation.mpp`) placed in a known folder on your machine.

## Import packages
First, import the classes we’ll need to interact with calendars and work weeks:

`Project` represents a Microsoft Project file, `Calendar` provides its calendars, `WorkWeek` defines a work‑week, and `WeekDay` represents a day.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## Step 1: set up your data directory
Define the folder that contains the `.mpp` file. Replace the placeholder with the actual path on your machine:

```java
String dataDir = "Your Data Directory";
```

## Step 2: create a Project instance and access the calendar
`Project` class represents a Microsoft Project file and provides access to its data structures, including calendars, tasks, and resources.  
Instantiate a `Project` object, pick the calendar you want (by UID), and obtain its `WorkWeekCollection`:

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **Pro tip:** If you’re not sure about the calendar UID, iterate through `project.getCalendars()` and print each calendar’s name and UID first.

## Step 3: iterate through work weeks
`WorkWeek` class encapsulates a work‑week definition, containing start/end dates and daily working‑time settings.  
Loop through each `WorkWeek` to display its name, start/end dates, and the daily working times:

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

**What you’ll see:** The console prints each work‑week’s label (e.g., “Standard”), its effective date range, and you can drill down to the exact working hours for each day.

## Common issues and solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` when accessing `calendar` | Wrong UID or calendar does not exist | Verify the UID with `project.getCalendars().size()` and list available calendars first. |
| No output for work weeks | The selected calendar has no custom work weeks (uses default) | Use the default calendar (`project.getDefaultCalendar()`) or create a work week programmatically. |
| Date format looks odd | `System.out.println` uses default `java.util.Date` format | Apply a `SimpleDateFormat` to format dates as needed. |

## Frequently asked questions
**Q: Can I modify the work weeks information using Aspose.Tasks for Java?**  
A: Yes. The API provides `addWorkWeek()`, `removeWorkWeek()`, and property setters to change names, dates, and working times.

**Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?**  
A: Absolutely. It supports MPP files from Project 98 up to the latest releases, as well as Project XML files.

**Q: Can I integrate Aspose.Tasks with other Java frameworks?**  
A: Yes. The library is pure Java, so you can use it alongside Spring, Jakarta EE, or any other framework.

**Q: Is there a trial version available for Aspose.Tasks?**  
A: Yes, you can download a free 30‑day trial from the official site: [Aspose.Tasks trial](https://releases.aspose.com/).

**Q: Where can I find support for Aspose.Tasks?**  
A: The Aspose community forum is the best place: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-08-13  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Retrieve Calendar Exceptions with Aspose.Tasks – asp tasks java tutorial](/tasks/java/calendar-exceptions/retrieve/)
- [How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks](/tasks/java/calendars/define-weekdays/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
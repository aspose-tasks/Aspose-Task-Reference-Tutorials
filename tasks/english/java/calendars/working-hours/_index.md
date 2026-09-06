---
date: 2026-08-24
description: Learn how to add holidays calendar, determine working days and calculate
  task duration by extracting working hours from MS Project calendars using Aspose.Tasks
  for Java.
images:
- /java/calendars/working-hours/og-image.png
keywords:
- add holidays calendar
- determine working days
- read ms project
- calculate task duration
- load mpp file
lastmod: 2026-08-24
linktitle: How to add holidays calendar and determine working days
og_description: Learn how to add holidays calendar, determine working days and calculate
  task duration by extracting working hours from MS Project calendars using Aspose.Tasks
  for Java.
og_image_alt: Guide to add holidays calendar and calculate task duration with Aspose.Tasks
  Java
og_title: How to add holidays calendar and determine working days
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
title: How to add holidays calendar and determine working days
url: /java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to add holidays calendar and determine working days

Managing project calendars is a core part of successful project planning. In this tutorial you’ll **add holidays calendar**, **determine working days** for any task, and **extract working hours** from an MS Project calendar using Aspose.Tasks for Java. By the end of the guide you’ll be able to **calculate task duration**, customize working hours, and reliably **load an MPP file** to retrieve the data you need—all without installing Microsoft Project.

## Quick answers
- **What does “determine working days” mean?** It means identifying which calendar dates are considered work‑days for a given task.  
- **Which library should I use?** Aspose.Tasks for Java provides a full‑featured API for working with MS Project files.  
- **How long does the implementation take?** Typically 10–15 minutes for a basic extraction.  
- **Do I need a license?** A free trial is available; a commercial license is required for production use.  
- **Can I customize working hours?** Yes – you can modify calendars, add holidays, and set custom work‑time ranges.  

## What is “determine working days”?
**Determine working days** means querying a project calendar to find out which dates are marked as work‑days versus non‑working days (weekends, holidays, or custom exceptions). This information is essential for accurate **calculate task duration** because only working days contribute to the elapsed time of a task.

## Why use Aspose.Tasks to retrieve working hours?
Aspose.Tasks lets you read MS Project files without Microsoft Project installed, enabling automation on any platform. It also provides high‑performance processing, extensive format support, and detailed documentation.  

- **Full calendar support** – default, resource, and task calendars are all accessible.  
- **High performance** – can process projects containing **10,000+ tasks in under 2 seconds** on a standard 2.5 GHz CPU.  
- **Extensive format coverage** – supports **50+ input and output formats**, including MPP, MPX, XML, and Primavera.  
- **Comprehensive documentation** – code samples, API reference, and community forums are all available.

## Prerequisites
Before you start, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or higher.  
2. **Aspose.Tasks for Java** – download the latest JAR from [Aspose.Tasks for Java releases](https://releases.aspose.com/tasks/java/).  
3. Basic Java programming knowledge.  

## Import packages
The `Project` class is Aspose.Tasks' top‑level object that represents a single MS Project file in memory. Import the required namespace before you begin:

Import Packages

```java
import com.aspose.tasks.*;
```

## How to load an MPP file with Aspose.Tasks?
The `Project` class loads an MS Project file and provides access to its data. Load the project file in a single line of code; no UI or COM interop is required. This straightforward step gives you full access to calendars, tasks, and resources.

Loading an MPP file

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Retrieve task and calendar information
`Task` represents a project task, and `Calendar` defines its working time rules. Select the task you want to analyse and obtain its associated calendar. The `Task` object provides `getStart()` and `getFinish()` methods, while the `Calendar` object exposes working time definitions.

Retrieving task and calendar

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Define start and end dates
`Date` objects specify the time window for calendar analysis. Set the time window for which you want to **determine working days**. Using the task’s start and finish dates ensures you only evaluate the relevant period.

Defining dates

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Iterate through dates
A `for` loop can iterate over each day in the date range. Loop through each date in the task’s duration. This loop will let you **customize working hours** later if needed and is the basis for calculating total work time.

Iterating dates

```java
java.util.Calendar tempDate = calStartDate;
```

## Calculate duration
`Duration` aggregates the total working time calculated from the iteration. During the iteration you check whether each day is a working day, sum the working hours, and finally compute the task’s duration in minutes, hours, and days. This demonstrates how to **calculate working days** and **calculate task duration** programmatically.

Calculating duration

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

## How to customize working hours and holidays
You can modify the calendar’s working time ranges and add exceptions such as holidays. Use `taskCalendar.addWorkingTime()` to set new work periods and `taskCalendar.addException()` to insert a holiday. This is useful when the default 9‑5 schedule does not match your organization’s policies.

## Common issues and solutions
| Issue | Solution |
|-------|----------|
| **Task returns `null` for calendar** | Ensure the task actually has a calendar assigned; otherwise it inherits the project’s default calendar. |
| **Incorrect duration because of holidays** | Verify that holidays are defined in the task’s calendar or in the project’s base calendar. |
| **Time zone mismatch** | Use `java.util.TimeZone` to align the calendar’s time zone with your system if needed. |

## Frequently asked questions
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures, including tasks, resources, and calendars.

### Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?
A: Absolutely, Aspose.Tasks for Java supports various MS Project versions, ensuring compatibility across different environments.

### Q: Can I customize working hours and holidays in project calendars?
A: Yes, you can easily customize working hours and holidays according to your project requirements using Aspose.Tasks for Java APIs.

### Q: Does Aspose.Tasks for Java offer support and documentation?
A: Yes, Aspose.Tasks for Java provides extensive documentation and dedicated support forums to assist developers in utilizing its features effectively.

### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can access a free trial version of Aspose.Tasks for Java from the [Aspose releases page](https://releases.aspose.com/).

## Conclusion
In this guide we demonstrated how to **add holidays calendar**, **determine working days**, **retrieve working hours**, and **calculate task duration** from an MS Project calendar using Aspose.Tasks for Java. By following the steps above you can automate schedule analysis, customize calendars, and keep your project plans accurate and up‑to‑date. You now have the tools to **read MS Project** data, **load an MPP file**, and perform precise duration calculations without the need for Microsoft Project itself.

---

**Last Updated:** 2026-08-24  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Related Tutorials

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Add Holidays to Calendar and Save as MPP with Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)
- [Create Custom Calendar Exceptions with Aspose.Tasks for Java](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
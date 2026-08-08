---
date: 2026-08-08
description: Learn how to set calendar ms project, set daily working hours, and add
  weekend working days using Aspose.Tasks for Java. Save the project as XML in just
  a few lines of code.
images:
- /java/calendars/define-weekdays/og-image.png
keywords:
- set calendar ms project
- set daily working hours
- add weekend working days
- java create msproject file
- aspose.tasks calendar
lastmod: 2026-08-08
linktitle: How to set calendar ms project and define weekdays
og_description: Set calendar ms project, define weekdays, and add weekend working
  days using Aspose.Tasks for Java. Follow this step‑by‑step tutorial and save as
  XML.
og_image_alt: Screenshot of Java code configuring MS Project calendar with Aspose.Tasks
og_title: Set calendar ms project with Aspose.Tasks – Java guide
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  headline: How to set calendar ms project and define weekdays
  type: TechArticle
- description: Learn how to set calendar ms project, set daily working hours, and
    add weekend working days using Aspose.Tasks for Java. Save the project as XML
    in just a few lines of code.
  name: How to set calendar ms project and define weekdays
  steps:
  - name: create a project instance
    text: Instantiate a `Project` object, which represents the MS Project file you
      will manipulate.
  - name: define a new calendar
    text: '`Calendar` represents a set of working times, exceptions, and holidays
      for a project.'
  - name: add standard working days (Monday‑Thursday)
    text: '`WeekDay` defines the working time for a specific day of the week.'
  - name: add weekend working days
    text: If your project runs on weekends, add Saturday and Sunday as regular working
      days. This demonstrates **add weekend working days**.
  - name: set a custom short working day (Friday)
    text: Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift
      (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.
  - name: save the project as XML
    text: '`SaveFileFormat` enumerates the supported file formats when saving a project,
      such as XML or MPP.'
  type: HowTo
- questions:
  - answer: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want
      to treat as a non‑working day.
    question: Can I define custom non‑working days using Aspose.Tasks for Java?
  - answer: Create `CalendarException` objects, specify the exception dates, and add
      them to `cal.getExceptions()`.
    question: How can I add holidays or company‑wide exceptions?
  - answer: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple
      Project versions.
    question: Is the library compatible with older MS Project versions?
  - answer: Load the project with `new Project("existing.mpp")`, retrieve the desired
      calendar, make changes, and save.
    question: Can I modify an existing calendar in an imported project?
  - answer: Yes, you can create and edit recurring tasks using the `RecurringTask`
      class.
    question: Does Aspose.Tasks handle recurring tasks as well?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- set calendar ms project
- aspose.tasks
- java project management
title: How to set calendar ms project and define weekdays
url: /java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to set calendar ms project and define weekdays

In this tutorial you’ll learn **how to set calendar ms project** programmatically, define weekdays, and configure custom working days using the Aspose.Tasks library for Java. Whether you’re building a scheduling engine, integrating with ERP systems, or simply need to generate a project plan without opening Microsoft Project, the steps below show you how to create a calendar, set daily working hours, and add weekend working days in a few lines of code.

## Quick answers
- **What library is required?** Aspose.Tasks for Java.  
- **Can I add weekend working days?** Yes – just mark Saturday and Sunday as working days.  
- **How do I save the project?** Call `prj.save(..., SaveFileFormat.Xml)`.  
- **Is a license needed?** A free trial works for evaluation; a license is required for production use.  
- **Which Java version is supported?** Java 8 or higher.

## What is set calendar ms project?
Setting the calendar in MS Project determines which days are considered working days, the number of working hours each day, and any special exceptions such as holidays or company‑wide shutdowns. This information drives task scheduling, resource allocation, and overall project timelines, ensuring that calculations respect the organization’s actual work patterns.

## Why use Aspose.Tasks for calendar manipulation?
Aspose.Tasks gives you programmatic control over calendars without launching the Microsoft Project UI. It runs on any operating system that supports Java, supports more than 50 input and output formats, and can process multi‑hundred‑page projects without loading the entire file into memory, making it ideal for server‑side automation.

## Prerequisites
- **Java Development Kit (JDK) 8+** – download from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
- **Aspose.Tasks for Java** – obtain the latest JAR from the [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
- An IDE or build tool (Maven/Gradle) to add the Aspose.Tasks JAR to your classpath.

## Import packages
Import the classes that provide access to projects, calendars, and working‑time objects.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Step‑by‑step guide

### Step 1: create a project instance
Instantiate a `Project` object, which represents the MS Project file you will manipulate.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Step 2: define a new calendar
`Calendar` represents a set of working times, exceptions, and holidays for a project.  

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Step 3: add standard working days (Monday‑Thursday)
`WeekDay` defines the working time for a specific day of the week.  

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Step 4: add weekend working days
If your project runs on weekends, add Saturday and Sunday as regular working days. This demonstrates **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Step 5: set a custom short working day (Friday)
Configure Friday with a morning shift (9 am‑12 pm) and an afternoon shift (1 pm‑4 pm) to illustrate **set daily working hours** and a custom short workday.

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### Step 6: save the project as XML
`SaveFileFormat` enumerates the supported file formats when saving a project, such as XML or MPP.  

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Common issues & solutions
| Issue | Solution |
|-------|----------|
| **Working times not applied** | Ensure `setDayWorking(true)` is called on each custom `WeekDay`. |
| **File not found when saving** | Verify that `dataDir` points to an existing folder and that the application has write permissions. |
| **Calendar not reflected in tasks** | Assign the newly created calendar to resources or tasks using `task.setCalendar(cal)`. |

## Frequently asked questions

**Q: Can I define custom non‑working days using Aspose.Tasks for Java?**  
A: Yes. Set the `DayWorking` property to `false` for any `WeekDay` you want to treat as a non‑working day.

**Q: How can I add holidays or company‑wide exceptions?**  
A: Create `CalendarException` objects, specify the exception dates, and add them to `cal.getExceptions()`.

**Q: Is the library compatible with older MS Project versions?**  
A: Absolutely. Aspose.Tasks supports MPP, MPT, and XML formats across multiple Project versions.

**Q: Can I modify an existing calendar in an imported project?**  
A: Load the project with `new Project("existing.mpp")`, retrieve the desired calendar, make changes, and save.

**Q: Does Aspose.Tasks handle recurring tasks as well?**  
A: Yes, you can create and edit recurring tasks using the `RecurringTask` class.

## Conclusion
You now know **how to set calendar ms project**, define weekdays, add weekend working days, and configure a short Friday schedule—all with Aspose.Tasks for Java. Save the result as XML and integrate the calendar logic into any Java‑based project‑management solution.

---

**Last Updated:** 2026-08-08  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose

## Related Tutorials

- [Add calendar to project with Aspose.Tasks for Java](/tasks/java/calendars/create/)
- [Determine Working Days & Working Hours with Aspose.Tasks](/tasks/java/calendars/working-hours/)
- [Add Holidays to Calendar and Save as MPP with Aspose.Tasks](/tasks/java/calendars/update-to-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
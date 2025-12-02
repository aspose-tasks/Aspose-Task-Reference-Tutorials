---
title: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to set calendar, define weekdays MS Project and set custom working days using Aspose.Tasks for Java. Save project as XML with just a few lines of code.
weight: 12
url: /java/calendars/define-weekdays/
date: 2025-12-02
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks

## Introduction
In this tutorial you’ll discover **how to set calendar** settings programmatically and define weekdays in a Microsoft Project file using the Aspose.Tasks library for Java. Whether you need to create a standard work week, add weekend working days, or configure a short Friday schedule, this guide walks you through every step—from project creation to saving the file as XML.

## Quick Answers
- **What library is needed?** Aspose.Tasks for Java  
- **Can I add weekend working days?** Yes – just add Saturday and Sunday as working days.  
- **How do I save the project?** Use `prj.save(..., SaveFileFormat.Xml)`.  
- **Do I need a license?** A free trial works for evaluation; a license is required for production.  
- **What Java version is required?** Java 8 or higher.

## What is “how to set calendar” in the context of MS Project?
Setting a calendar in MS Project means defining which days are working days, the daily working hours, and any exceptions such as holidays. This calendar drives task scheduling, resource allocation, and overall project timelines.

## Why use Aspose.Tasks for calendar manipulation?
- **Full control** – programmatically create, modify, or delete calendars without opening the UI.  
- **Cross‑platform** – works on any OS that supports Java.  
- **Supports all file formats** – MPP, MPT, and XML, so you can *save project as XML* for easy integration with other systems.  
- **No COM dependencies** – unlike the Microsoft Project Interop library.

## Prerequisites
Before you start, make sure you have:

1. **Java Development Kit (JDK) 8+** – download from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. **Aspose.Tasks for Java** – obtain the latest JAR from the [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. An IDE or build tool (Maven/Gradle) to add the Aspose.Tasks JAR to your project’s classpath.

## Import Packages
First, import the classes you’ll need. These imports give you access to project, calendar, and working‑time objects.

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## Step‑by‑Step Guide

### Step 1: Create a Project Instance
Create a new `Project` object. This object represents the MS Project file you’ll be editing.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### Step 2: Define a New Calendar
Add a fresh calendar to the project. Giving it a clear name helps when you have multiple calendars.

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### Step 3: Add Standard Working Days (Monday‑Thursday)
Use the built‑in helper `WeekDay.createDefaultWorkingDay` to set the default 9 am‑5 pm schedule for the core work week.

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### Step 4: Add Weekend Working Days
If your project runs on weekends, simply add Saturday and Sunday as regular working days. This demonstrates **add weekend working days**.

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### Step 5: Set a Custom Short Working Day (Friday)
Here we **set custom working days** for Friday: a morning shift (9 am‑12 pm) and an afternoon shift (1 pm‑4 pm).

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

### Step 6: Save the Project as XML
Finally, persist the changes. The `SaveFileFormat.Xml` option lets you **save project as XML**, which is useful for integration with other tools.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Working times not applied** | Ensure `setDayWorking(true)` is called on the custom `WeekDay`. |
| **File not found when saving** | Verify that `dataDir` points to an existing folder and that your application has write permissions. |
| **Calendar not reflected in tasks** | Assign the newly created calendar to resources or tasks using `task.setCalendar(cal)`. |

## Frequently Asked Questions

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
You now know **how to set calendar** settings, **define weekdays MS Project**, add weekend working days, and create a short Friday schedule—all with Aspose.Tasks for Java. Save the result as XML and integrate the calendar logic into any Java‑based project management solution.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
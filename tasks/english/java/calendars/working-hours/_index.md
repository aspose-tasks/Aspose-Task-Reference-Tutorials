---
title: Determine Working Days & Working Hours with Aspose.Tasks
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to determine working days and calculate task duration by extracting working hours from MS Project calendars using Aspose.Tasks for Java.
weight: 13
url: /java/calendars/working-hours/
date: 2025-12-05
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Determine Working Days & Working Hours with Aspose.Tasks

## Introduction
Managing project calendars is a core part of successful project planning. In this tutorial you’ll **determine working days** for any task and **extract working hours** from an MS Project calendar using Aspose.Tasks for Java. By the end of the guide you’ll be able to **calculate task duration**, customize working hours, and reliably **load an MPP file** to retrieve the data you need.

## Quick Answers
- **What does “determine working days” mean?** It means identifying which calendar dates are considered work‑days for a given task.  
- **Which library should I use?** Aspose.Tasks for Java provides a full‑featured API for working with MS Project files.  
- **How long does the implementation take?** Typically 10–15 minutes for a basic extraction.  
- **Do I need a license?** A free trial is available; a commercial license is required for production use.  
- **Can I customize working hours?** Yes – you can modify calendars, add holidays, and set custom work‑time ranges.

## What is “determine working days”?
When a task is scheduled, the project calendar defines which days are work days and which are non‑working (weekends, holidays). Determining working days means querying that calendar to know exactly when work can occur, which is essential for accurate **calculate task duration** calculations.

## Why use Aspose.Tasks to retrieve working hours?
- **No Microsoft Project required** – work with .MPP files on any platform.  
- **Full calendar support** – includes default, resource, and task calendars.  
- **High performance** – process large projects quickly.  
- **Extensive documentation** – examples and API reference are readily available.

## Prerequisites
Before you start, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or higher.  
2. **Aspose.Tasks for Java** – download the latest JAR from [here](https://releases.aspose.com/tasks/java/).  
3. Basic Java programming knowledge.  

## Import Packages
First, import the core Aspose.Tasks namespace:

```java
import com.aspose.tasks.*;
```

## Step 1: Load the MPP file
Load your project file (the **load mpp file** step) so you can work with its calendars:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Step 2: Retrieve Task and Calendar Information
Pick the task you want to analyse and get its associated calendar. This is where we **retrieve working hours** for the task:

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## Step 3: Define Start and End Dates
Set up the time window for which you want to **determine working days**:

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## Step 4: Iterate Through Dates
Loop through each date in the task’s duration. This loop will help us **customize working hours** later if needed:

```java
java.util.Calendar tempDate = calStartDate;
```

## Step 5: Calculate Duration
During the iteration we check whether each day is a working day, sum the working hours, and finally compute the task’s duration in minutes, hours, and days:

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

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Task returns `null` for calendar** | Ensure the task actually has a calendar assigned; otherwise it inherits the project’s default calendar. |
| **Incorrect duration because of holidays** | Verify that holidays are defined in the task’s calendar or in the project’s base calendar. |
| **Time zone mismatch** | Use `java.util.TimeZone` to align the calendar’s time zone with your system if needed. |

## Frequently Asked Questions
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures, including tasks, resources, and calendars.

### Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?
A: Absolutely, Aspose.Tasks for Java supports various versions of MS Project, ensuring compatibility across different environments.

### Q: Can I customize working hours and holidays in project calendars?
A: Yes, you can easily customize working hours and holidays according to your project requirements using Aspose.Tasks for Java APIs.

### Q: Does Aspose.Tasks for Java offer support and documentation?
A: Yes, Aspose.Tasks for Java provides extensive documentation and dedicated support forums to assist developers in utilizing its features effectively.

### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can access a free trial version of Aspose.Tasks for Java from [here](https://releases.aspose.com/).

## Conclusion
In this guide we demonstrated how to **determine working days**, **retrieve working hours**, and **calculate task duration** from an MS Project calendar using Aspose.Tasks for Java. By following the steps above you can automate schedule analysis, customize calendars, and keep your project plans accurate and up‑to‑date.

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
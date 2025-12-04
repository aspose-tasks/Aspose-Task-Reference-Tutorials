---
title: How to Set Project Calendar with Aspose.Tasks for Java
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to set project calendar and manage MS Project calendar properties in Java using Aspose.Tasks. Step‑by‑step guide to display calendar working hours and customize schedules.
weight: 10
url: /java/calendars/properties/
date: 2025-12-04
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set Project Calendar with Aspose.Tasks for Java

## Introduction
In this tutorial you'll discover **how to set project calendar** programmatically using the Aspose.Tasks library for Java. Controlling calendar properties lets you **display calendar working hours**, define custom working days, and align your project schedule with real‑world constraints. We'll walk through every step—from setting up the environment to iterating over calendars and reading their properties—so you can confidently manage MS Project calendars in your applications.

## Quick Answers
- **What does “set project calendar” mean?** It means creating or updating a calendar's working times, base calendar, and day types within an MS Project file.  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Can I display calendar working hours?** Yes—by reading each `WeekDay` you can output the hours for every day type.  
- **Is this compatible with Maven/Gradle?** Absolutely—add the Aspose.Tasks JAR as a dependency.

## What Is a Project Calendar?
A project calendar defines the working days and hours for tasks, resources, and the overall project timeline. In MS Project, calendars can inherit from a base calendar, and each day type (e.g., **Standard**, **Non‑working**) can have its own working time. Managing these settings programmatically enables dynamic schedule adjustments without manual editing.

## Why Manage MS Project Calendar Programmatically?
- **Automation:** Adjust calendars across many projects with a single script.  
- **Consistency:** Enforce organization‑wide working time policies.  
- **Integration:** Sync calendars with external systems (HR, ERP).  
- **Visibility:** Quickly **display calendar working hours** for reporting or debugging.

## Prerequisites
Before you start, make sure you have:

- **Java Development Kit (JDK) 8+** installed and `JAVA_HOME` configured.  
- **Aspose.Tasks for Java** library downloaded from the [download page](https://releases.aspose.com/tasks/java/). Add the JAR to your project's classpath or Maven/Gradle dependencies.  

## Import Packages
First, import the core Aspose.Tasks classes that we’ll use throughout the tutorial:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up the Data Directory
Define the folder that contains your project files. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

## Step 2: Define Time Units
Working times are expressed in milliseconds. Defining reusable constants makes the code easier to read.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Step 3: Load Project Data
Create a `Project` instance by loading an existing MS Project XML file (`.xml` or `.mpp`). This gives us access to all calendars stored in the file.

```java
Project project = new Project(dataDir + "project.xml");
```

## Step 4: Iterate Through Calendars and Display Working Hours
Now we loop through every calendar, print its unique identifier, name, base calendar, and the working hours for each day type. This demonstrates **how to set project calendar** values and also how to **display calendar working hours**.

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### What This Code Does
- **Filters unnamed calendars** (some internal calendars may have a `null` name).  
- **Prints UID and name** – useful for identifying the calendar later.  
- **Shows the base calendar** – either “Self” (the calendar is its own base) or the name of the inherited calendar.  
- **Loops through each `WeekDay`** to calculate and output the total working hours (`workingTime` is in milliseconds, so we divide by `OneHour`).  

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | Calendar is a base calendar itself (`isBaseCalendar()` returns `true`). | Use the ternary check as shown (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | The project file uses a different time unit (ticks). | Verify the file format; Aspose.Tasks normalizes to milliseconds, but ensure you’re loading the correct file type. |
| Unable to locate `project.xml` | Incorrect `dataDir` path. | Use an absolute path or `Paths.get(dataDir, "project.xml").toString()`. |

## Frequently Asked Questions

**Q: Can I modify calendar properties programmatically using Aspose.Tasks?**  
A: Yes, the API provides full read/write access to calendars, allowing you to add, edit, or delete working times, exceptions, and base calendar relationships.

**Q: Are there any limitations to calendar customization with Aspose.Tasks?**  
A: The library mirrors the capabilities of Microsoft Project, so you can customize virtually all calendar aspects. Only very old Project file versions may have minor compatibility quirks.

**Q: Can I integrate calendar management into existing Java projects?**  
A: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use the same code patterns shown here.

**Q: Does Aspose.Tasks support other project management functionalities besides calendar management?**  
A: Yes, it covers tasks, resources, assignments, outlines, baselines, and more—making it a comprehensive solution for Java‑based project automation.

**Q: Is technical support available for developers using Aspose.Tasks?**  
A: Yes, Aspose provides dedicated forums, email support, and extensive documentation for all licensed users.

## Conclusion
By following this guide you now know **how to set project calendar** values, read and **display calendar working hours**, and integrate these capabilities into any Java application using Aspose.Tasks. This empowers you to automate schedule adjustments, enforce consistent working policies, and build richer project‑management solutions.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
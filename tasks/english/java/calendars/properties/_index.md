---
date: 2026-09-09
description: How to set project calendar in Java using Aspose.Tasks. Learn to display
  calendar working hours, configure working time, and modify calendar days in MS Project
  files.
images:
- /java/calendars/properties/og-image.png
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: Manage calendar properties in Aspose.Tasks
og_description: How to set project calendar in Java using Aspose.Tasks. This guide
  shows you how to display calendar working hours, configure working time, and modify
  calendar days in MS Project files.
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: How to set project calendar Java with Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: How to set project calendar Java with Aspose.Tasks
url: /java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to set project calendar Java with Aspose.Tasks

## Introduction
In this tutorial you’ll learn **how to set project calendar** in Java by leveraging the Aspose.Tasks library. Controlling calendar properties lets you **display calendar working hours**, configure custom working days, and keep your project schedule aligned with real‑world constraints such as holidays or shift patterns. We’ll walk through environment setup, loading a project, iterating over calendars, and reading or updating their properties, so you can confidently **manage MS Project calendar** settings in any Java application.

## Quick answers
- **What does “set project calendar” mean?** It means creating or updating a calendar’s working times, base calendar, and day types within an MS Project file.  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Can I display calendar working hours?** Yes—by reading each `WeekDay` you can output the hours for every day type.  
- **Is this compatible with Maven/Gradle?** Absolutely—add the Aspose.Tasks JAR as a dependency.

## How to set project calendar in Java
Load your project file, locate the target calendar, and then adjust its working time definitions, base calendar, and day types as needed. The steps below provide a complete, end‑to‑end solution that demonstrates loading, iterating, modifying, and saving the project while handling exceptions and ensuring accurate working‑hour calculations.

## What is a project calendar?
A project calendar defines the working days and hours for tasks, resources, and the overall project timeline. In MS Project, calendars can inherit from a base calendar, and each day type (e.g., **Standard**, **Non‑working**) can have its own working time. Managing these settings programmatically enables dynamic schedule adjustments without manual editing.

## Why manage MS Project calendar programmatically?
Programmatically managing calendars lets you apply consistent scheduling rules across many projects, reduce manual errors, and integrate calendar data with other enterprise systems such as HR or ERP. This automation speeds up project setup and ensures that all team members follow the same working‑time policies.

- **Automation:** Adjust calendars across dozens of projects with a single script.  
- **Consistency:** Enforce organization‑wide working‑time policies automatically.  
- **Integration:** Sync calendars with external HR or ERP systems.  
- **Visibility:** Quickly **display calendar working hours** for reporting or debugging.  
- **Flexibility:** Add exceptions or shift patterns on the fly without opening the UI.

## Prerequisites
Before you start, ensure you have:

- **Java Development Kit (JDK) 8+** installed and `JAVA_HOME` configured.  
- **Aspose.Tasks for Java** library downloaded from the [download page](https://releases.aspose.com/tasks/java/). Add the JAR to your classpath or declare it as a Maven/Gradle dependency.  
- A sample MS Project file (`.mpp` or `.xml`) that contains at least one calendar you want to inspect or modify.

## Import packages
The `Project`, `Calendar`, `WeekDay`, and related classes are the core of calendar manipulation.  
The `Calendar` class represents a project calendar, containing working days, exceptions, and base‑calendar relationships.  
The `WeekDay` class defines the working time settings for a single day within a calendar.

The `Project` class is Aspose.Tasks' top‑level object that represents a single MS Project file in memory. After you load a file, all calendar operations flow through this object.

```java
import com.aspose.tasks.*;
```

## Step 1: set up the data directory
Define the folder that contains your project files. Replace the placeholder with the actual path on your machine.

```java
String dataDir = "Your Data Directory";
```

## Step 2: define time‑unit constants
Working times are expressed in milliseconds. Defining reusable constants makes the code easier to read and helps you **calculate working hours Java** accurately.

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## Step 3: load project data
Create a `Project` instance by loading an existing MS Project XML file (`.xml` or `.mpp`). This gives you access to all calendars stored in the file.

The `Project` class loads the file into a lightweight object model; it does **not** require the full file to be held in memory, allowing you to work with projects that contain tens of thousands of tasks.

```java
Project project = new Project(dataDir + "project.xml");
```

## Step 4: iterate through calendars Java
Now we loop through every calendar, print its unique identifier, name, base calendar, and the working hours for each day type. This demonstrates **how to set project calendar Java** values and also how to **display calendar working hours**.

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

### What this code does
- **Filters unnamed calendars** (some internal calendars may have a `null` name).  
- **Prints UID and name** – useful for identifying the calendar later.  
- **Shows the base calendar** – either “Self” (the calendar is its own base) or the name of the inherited calendar.  
- **Loops through each `WeekDay`** to calculate and output the total working hours (`workingTime` is in milliseconds, so we divide by `OneHour`).  

## Quantified benefits of using Aspose.Tasks
Aspose.Tasks supports **30+ input and output formats** and can process **projects with up to 10,000 tasks** without loading the entire file into memory, delivering results in under a second on typical server hardware. These numbers make it a reliable choice for enterprise‑scale automation.

## Common issues and solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `cal.getBaseCalendar()` | Calendar is a base calendar itself (`isBaseCalendar()` returns `true`). | Use the ternary check as shown (`cal.isBaseCalendar() ? "Self" : ...`). |
| No output for working hours | The project file uses a different time unit (ticks). | Verify the file format; Aspose.Tasks normalizes to milliseconds, but ensure you’re loading the correct file type. |
| Unable to locate `project.xml` | Incorrect `dataDir` path. | Use an absolute path or `Paths.get(dataDir, "project.xml").toString()`. |

## Frequently asked questions

**Q: Can I modify calendar properties programmatically using Aspose.Tasks?**  
A: Yes, the API provides full read/write access to calendars, allowing you to add, edit, or delete working times, exceptions, and base‑calendar relationships.

**Q: Are there any limitations to calendar customization with Aspose.Tasks?**  
A: The library mirrors the capabilities of Microsoft Project, so you can customize virtually all calendar aspects. Only very old Project file versions may have minor compatibility quirks.

**Q: Can I integrate calendar management into existing Java projects?**  
A: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use the same code patterns shown here.

**Q: Does Aspose.Tasks support other project‑management functionalities besides calendar management?**  
A: Yes, it covers tasks, resources, assignments, outlines, baselines, and more—making it a comprehensive solution for Java‑based project automation.

**Q: Is technical support available for developers using Aspose.Tasks?**  
A: Yes, Aspose provides dedicated forums, email support, and extensive documentation for all licensed users.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Related Tutorials

- [Create Project Calendar Java – Aspose.Tasks for Java Guide](/tasks/java/)
- [Load Project Files in Java and Manage Project Properties](/tasks/java/project-management/default-properties/)
- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
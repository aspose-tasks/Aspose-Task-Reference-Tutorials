---
title: Add calendar to project with Aspose.Tasks for Java
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to add calendar to project, how to create MS Project calendar, and save project as XML using Aspose.Tasks for Java.
weight: 11
url: /java/calendars/create/
date: 2025-12-02
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add calendar to project with Aspose.Tasks for Java

## Introduction
In modern project‑management workflows, the ability to **add calendar to project** programmatically can save hours of manual editing. Aspose.Tasks for Java gives developers a clean, type‑safe API to manipulate Microsoft Project files without ever opening the desktop client. In this tutorial you’ll learn **how to add calendar**, **how to create MS Project calendar**, and **save project as XML**—all with just a few lines of Java code.

## Quick Answers
- **What does “add calendar to project” mean?**  
  It means inserting a new working‑time definition (calendar) into a Microsoft Project file via code.  
- **Which library handles this?**  
  Aspose.Tasks for Java provides the `Calendar` class and `Project` container to manage calendars.  
- **Do I need a license?**  
  A temporary evaluation license works for testing; a full license is required for production use.  
- **Can I save the file as XML?**  
  Yes—use `SaveFileFormat.Xml` to export the project as an XML file.  
- **What are the prerequisites?**  
  Java JDK 8+ and the Aspose.Tasks for Java JAR on your classpath.

## What is “add calendar to project”?
Adding a calendar to a project creates a custom schedule that defines working days, holidays, and daily work hours. This calendar can then be assigned to tasks, resources, or the entire project, ensuring that calculations such as start dates and durations respect the defined working time.

## Why use Aspose.Tasks for Java to add calendar to project?
- **Full control** – No UI required; automate bulk calendar creation across many projects.  
- **Cross‑version compatibility** – Works with Project 2007, 2010, 2013, 2016, and later files.  
- **No Microsoft Project installation** – Run on any server or CI pipeline.  
- **Export flexibility** – Save as XML, MPP, or other supported formats.

## Prerequisites
- **Java Development Kit (JDK) 8 or newer** installed and configured.  
- **Aspose.Tasks for Java** library – download from the [official website](https://releases.aspose.com/tasks/java/) and add the JAR to your project’s classpath.  
- An IDE or build tool (Maven/Gradle) of your choice.

## Step‑by‑step guide

### Step 1: Import the required Aspose.Tasks package
First, bring the Aspose.Tasks classes into scope so you can work with projects and calendars.

```java
import com.aspose.tasks.*;
```

### Step 2: Set the data directory path
Define where the generated project file will be written. Replace the placeholder with an absolute or relative path on your machine.

```java
String dataDir = "Your Data Directory";
```

### Step 3: Create a new Project instance
Instantiate a `Project` object – this represents an empty Microsoft Project file that you can populate.

```java
Project prj = new Project();
```

### Step 4: Define the calendars you want to add
Use the `Calendars.add(String name)` method to create new calendar entries. In this example we add three calendars, but you can add as many as needed and configure their working times later.

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **Pro tip:** After adding a calendar, you can customize its working days with `cal1.getWeekDays().add(...)` and set daily work hours using `cal1.getBaseCalendar().setWorkingTime(...)`.

### Step 5: Save the project (save project as XML)
Persist the project, including the newly added calendars, to an XML file. This format is easy to inspect and compatible with many tools.

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 6: Display a completion message
Let the user know the operation finished successfully.

```java
System.out.println("Process completed Successfully");
```

By following these six concise steps, you have successfully **added a calendar to a project** and saved the result as an XML file.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `prj.getCalendars()`** | Project object not initialized correctly. | Ensure `new Project()` is called before accessing calendars. |
| **File not found when saving** | `dataDir` points to a non‑existent folder. | Create the directory first or use an absolute path. |
| **Calendar name appears as “no info”** | Placeholder names were used in the sample. | Replace with meaningful names that reflect the schedule (e.g., “US Holiday Calendar”). |
| **Saved XML cannot be opened in MS Project** | Using an outdated Aspose.Tasks version. | Update to the latest Aspose.Tasks for Java release. |

## Frequently Asked Questions

**Q: Can Aspose.Tasks handle complex calendars with multiple exceptions?**  
A: Yes – after adding a calendar you can define exceptions, working hours, and non‑working days using the `WeekDay` and `Exception` classes.

**Q: Is it possible to assign the new calendar to specific tasks?**  
A: Absolutely. Retrieve a task via `prj.getRootTask().getChildren().add("Task Name")` and set `task.set(Tsk.CALENDAR, cal3);`.

**Q: Does the library support saving in other formats like MPP?**  
A: Yes. Replace `SaveFileFormat.Xml` with `SaveFileFormat.Mpp` or `SaveFileFormat.P6` as needed.

**Q: Do I need a license for development builds?**  
A: A temporary evaluation license is sufficient for testing; a full license is required for production deployments.

**Q: Where can I get help if I run into issues?**  
A: The Aspose.Tasks community forum is an excellent resource: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
Using Aspose.Tasks for Java, you can programmatically **add calendar to project**, customize scheduling rules, and **save project as XML** with just a few lines of code. This automation reduces manual effort, eliminates human error, and enables batch processing of large project portfolios.

---

**Last Updated:** 2025-12-02  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
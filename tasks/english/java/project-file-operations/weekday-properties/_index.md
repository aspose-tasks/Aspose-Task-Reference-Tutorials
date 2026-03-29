---
title: Change Days Per Month with Aspose.Tasks Weekday Properties
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to change days per month and manage other weekday properties in Aspose.Tasks for Java. Customize week start dates, modify project calendar, and save project as XML.
weight: 25
url: /java/project-file-operations/weekday-properties/
date: 2026-03-29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Change Days Per Month with Aspose.Tasks Weekday Properties

## Introduction
Aspose.Tasks for Java lets you **change days per month** and fine‑tune other weekday settings without needing Microsoft Project installed. Whether you’re aligning a project calendar to a non‑standard fiscal month or simply need to adjust the week start day, this tutorial walks you through the most common scenarios—retrieving the current week start day, customizing the week start date, modifying the project calendar, and saving the project as XML.

## Quick Answers
- **Can I change the number of days per month?** Yes, use `Prj.DAYS_PER_MONTH` on the `Project` object.  
- **How do I customize the week start date?** Set `Prj.WEEK_START_DAY` to a `DayType` value (e.g., `DayType.Monday`).  
- **What format can I use to export the project?** The example saves the file as XML with `SaveFileFormat.Xml`.  
- **Is a license required for production use?** A valid Aspose.Tasks license is needed for non‑evaluation deployments.  
- **Which IDEs are supported?** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans works.

## What is “change days per month” in Aspose.Tasks?
Changing days per month means updating the `Prj.DAYS_PER_MONTH` property of a `Project` instance. This property tells the engine how many working days it should consider in each month, which directly affects task scheduling and cost calculations.

## Why modify project calendar properties?
Customizing the project calendar—like setting a different week start day or altering minutes per day—helps you:

- Align schedules with regional workweeks.  
- Model non‑standard work patterns (e.g., 4‑day weeks).  
- Ensure accurate reporting for contracts that use custom calendars.

## Prerequisites
- **Java Development Kit (JDK)** – Install the latest JDK from Oracle.  
- **Aspose.Tasks for Java library** – Download it from the official site [here](https://releases.aspose.com/tasks/java/).  
- **IDE of your choice** – IntelliJ IDEA, Eclipse, or NetBeans.

## Import Packages
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Load Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
This loads an existing Microsoft Project file (`project.mpp`) from the folder you specify.

## Step 2: Display Weekday Properties
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Here we retrieve and print the current weekday settings, including the **week start day** and **days per month**.

## Step 3: Setting Weekday Properties
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
In this step we **change days per month** to 24, set the week to start on Monday, and adjust the minutes per day/week. This demonstrates how to **modify project calendar** values programmatically.

## Step 4: Save Project
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
The modified project is persisted using the **save project as XML** format, which is handy for integration with other tools or for version‑controlled storage.

## Step 5: Display Result
```java
System.out.println("Process completed Successfully");
```
A simple confirmation that the operations finished without errors.

## How to Customize Week Start Date
If your organization follows a Sunday‑first calendar, replace `DayType.Monday` with `DayType.Sunday`. The same property (`Prj.WEEK_START_DAY`) is used, making the change straightforward.

## How to Retrieve Week Start Day
You can call `project.get(Prj.WEEK_START_DAY)` at any point to **retrieve week start day** information, as shown in Step 2.

## How to Modify Project Calendar
Beyond the week start day, you can also adjust `Prj.MINUTES_PER_DAY` and `Prj.MINUTES_PER_WEEK` to reflect custom working hours or shift patterns.

## Common Issues and Solutions
- **Incorrect day type value** – Ensure you use the `DayType` enum (e.g., `DayType.Monday`).  
- **File path errors** – Verify that `dataDir` ends with the appropriate file separator (`/` or `\`).  
- **License not set** – If you see licensing warnings, register your Aspose.Tasks license before creating the `Project` object.

## Frequently Asked Questions

**Q: Can Aspose.Tasks for Java handle complex project structures?**  
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures with ease.

**Q: Is Aspose.Tasks for Java compatible with different versions of Microsoft Project files?**  
A: Absolutely, Aspose.Tasks for Java supports various versions of Microsoft Project files, ensuring compatibility across platforms.

**Q: Can I integrate Aspose.Tasks for Java into my existing Java applications?**  
A: Yes, Aspose.Tasks for Java offers seamless integration capabilities, allowing you to enhance your Java applications with powerful project management features.

**Q: Does Aspose.Tasks for Java provide documentation and support?**  
A: Yes, you can access extensive documentation and community support for Aspose.Tasks for Java on their [website](https://releases.aspose.com/).

**Q: Is there a free trial available for Aspose.Tasks for Java?**  
A: Yes, you can download a free trial version of Aspose.Tasks for Java from their [website](https://reference.aspose.com/tasks/java/) to explore its features before making a purchase.

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
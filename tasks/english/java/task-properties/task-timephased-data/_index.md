---
title: How to Use Aspose.Tasks to Manage Task Timephased Data (Java)
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to use Aspose.Tasks for Java to manage task timephased data, download the library, try it free, and streamline project tracking.
weight: 34
url: /java/task-properties/task-timephased-data/
date: 2026-02-28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Use Aspose.Tasks for Task Timephased Data

## Introduction
If you’re looking for **how to use Aspose** to keep a tight grip on your project schedule, you’ve come to the right place. Precise tracking of task timephased data is a cornerstone of successful project management, and Aspose.Tasks for Java gives you the tools you need to automate that process. In this tutorial we’ll walk through a complete, end‑to‑end example that shows you how to use Aspose.Tasks to create a project, assign resources, set baselines, and finally retrieve and display timephased data.

## Quick Answers
- **What does “timephased data” mean?** It’s data broken down by time intervals (days, weeks, months) that shows work, cost, or remaining work over the project timeline.  
- **Which library provides this capability?** Aspose.Tasks for Java.  
- **Do I need a license to run the sample?** A free trial works for development; a license is required for production.  
- **What Java version is required?** Java 8 or higher.  
- **Can I export the results to Excel?** Yes – you can iterate the `TimephasedData` collection and write values to any format you need.

## What is Task Timephased Data?
Task timephased data represents the amount of work (or cost) scheduled for a task during each time slice of the project calendar. It enables you to see how work is distributed, spot overallocation, and compare planned vs. actual progress.

## Why Use Aspose.Tasks to Manage Timephased Data?
- **Full control** – programmatically create, modify, and query timephased information without opening Microsoft Project.  
- **Cross‑platform** – works on any OS that supports Java.  
- **No COM dependencies** – ideal for server‑side automation.  
- **Rich API** – supports baselines, work contours, and custom fields out of the box.

## Prerequisites
Before diving into the code, make sure you have:

- **Java Development Environment** – JDK 8+ installed and `JAVA_HOME` configured.  
- **Aspose.Tasks for Java Library** – Download and include the Aspose.Tasks library in your project. You can find the library [here](https://releases.aspose.com/tasks/java/).  
- **Document Directory** – A folder on your machine where the sample project file (`project.xml`) will be read from and written to.

## Import Packages
In your Java project, import the necessary Aspose.Tasks classes:

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explanation:* We create a `Project` instance, initialise a `Calendar` to the desired start date, and assign it to the project’s `START_DATE` property.

## Step 2: Define Task and Resource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explanation:* A new task named **Task** is added under the root task. We also create a resource called **Rsc** and set its standard and overtime rates.

## Step 3: Set Task Duration
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explanation:* The task is scheduled for a duration of **6 days**.

## Step 4: Assign Resource to Task
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explanation:* The previously defined resource is linked to the task via a `ResourceAssignment`.

## Step 5: Configure Resource Assignment
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explanation:* We set the assignment’s stop and resume dates (using a placeholder value) and apply a **Back‑Loaded** work contour, which shifts more work toward the end of the assignment.

## Step 6: Set Baseline
```java
project.setBaseline(BaselineType.Baseline);
```
*Explanation:* Capturing a baseline allows you to compare planned vs. actual values later on.

## Step 7: Update Task Completion
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explanation:* The task is marked as **50 % complete**, which will affect the remaining work calculations.

## Step 8: Retrieve Timephased Data
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explanation:* This call pulls the **remaining work** for the assignment, broken down by the project’s time intervals.

## Step 9: Display Timephased Data
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explanation:* We simply print the number of timephased entries and the value of the first entry. In a real‑world scenario you would iterate the list and export the data to a report or UI.

## Common Issues and Solutions
- **NullPointerException on `getTimephasedData`** – Ensure the assignment’s `START` and `FINISH` dates are set before calling the method.  
- **Incorrect work contour** – Verify that the `WorkContourType` you choose matches your scheduling strategy; `BackLoaded` is just one of several options.  
- **Baseline not reflecting changes** – Remember to call `project.setBaseline` *after* you have defined tasks, resources, and assignments.

## Frequently Asked Questions
### Q: Can I use Aspose.Tasks for Java in any Java project?
A: Yes, Aspose.Tasks for Java is compatible with any Java‑based project.

### Q: Where can I find additional support for Aspose.Tasks for Java?
A: Visit the [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) for support and discussions.

### Q: Is there a free trial available for Aspose.Tasks for Java?
A: Yes, you can explore a free trial [here](https://releases.aspose.com/).

### Q: How can I obtain a temporary license for Aspose.Tasks for Java?
A: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Q: Where can I purchase Aspose.Tasks for Java?
A: You can purchase Aspose.Tasks for Java [here](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
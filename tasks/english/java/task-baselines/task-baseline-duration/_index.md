---
title: How to Set Baseline Duration in Aspose.Tasks for Java
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
description: Learn how to set baseline duration and create project instance using Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines efficiently.
weight: 12
url: /java/task-baselines/task-baseline-duration/
date: 2026-01-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set Baseline Duration in Aspose.Tasks for Java

## Introduction
Setting a baseline is a fundamental step to track project progress against the original plan. In this tutorial you’ll learn **how to set baseline** duration for tasks in Microsoft Project using the Aspose.Tasks library for Java, and see why establishing a baseline early can save you time and headaches later.

## Quick Answers
- **What does “set baseline” mean?** It records the original start, finish, and duration of a task so you can compare future changes.  
- **Which Aspose.Tasks class creates a project?** The `Project` class – you’ll also learn how to **create project instance** correctly.  
- **Do I need a license to run the code?** A free evaluation license works for testing; a commercial license is required for production.  
- **Can I retrieve interim baselines?** Yes, Aspose.Tasks lets you query interim baselines and their fixed costs.  
- **What Java version is required?** Java 8 or later is recommended.

## What is a task baseline and why set it?
A task baseline captures the planned schedule (start date, finish date, and duration) at a specific point in time. By setting a baseline you create a reference point that makes it easy to spot schedule drift, cost overruns, and resource overallocation as the project evolves.

## Why use Aspose.Tasks for baseline management?
- **Full .mpp compatibility** – read and write native Microsoft Project files without Office installed.  
- **Rich API** – access baseline data, interim baselines, and time‑phased information programmatically.  
- **Cross‑platform** – works on Windows, Linux, and macOS with any standard JDK.

## Prerequisites
1. **Java Development Environment** – JDK 8+ installed and configured.  
2. **Aspose.Tasks for Java** – download the library from [here](https://releases.aspose.com/tasks/java/).  
3. **IDE or build tool** – Maven, Gradle, or any IDE you prefer.

## Import Packages
First, import the necessary classes into your Java project:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Step 1: Create a Project Instance
Creating a project instance is the foundation for any further manipulation. This step shows how to **create project instance** using Aspose.Tasks:

```java
Project project = new Project();
```

## Step 2: Create a Task Baseline
Add a new task to the project’s root and set its baseline. This records the original schedule for the task:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Step 3: Display Task Baseline Information
Retrieve the baseline you just created and print its key properties. This helps you verify that the baseline was set correctly:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Step 4: Check Interim Baseline and Fixed Cost
If you’re working with interim baselines, you can query whether the current baseline is interim and any associated fixed cost:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Step 5: Print Timephased Data
Time‑phased data shows how the baseline is distributed over time. Loop through the collection to inspect each entry:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

By following these steps, you can **how to set baseline** duration for any task and retrieve detailed baseline information using Aspose.Tasks for Java.

## Common Issues and Solutions
- **Baseline not appearing in MS Project:** Ensure you called `project.setBaseline(BaselineType.Baseline)` **after** adding the task.  
- **NullPointerException on `getBaselines()`:** Verify that the task was added to the project before setting the baseline.  
- **Time unit mismatch:** Use `TimeUnitType` to format the duration correctly, especially when working with custom calendars.

## FAQ's
### What is a task baseline in MS Project?
A task baseline in MS Project is a snapshot of the initial planned schedule for a task, including its start date, finish date, and duration.

### Why is managing task baselines important?
Managing task baselines helps in comparing the planned schedule with the actual progress of the project, facilitating better tracking and decision‑making.

### Can I modify a task baseline once it's set?
Yes, you can modify task baselines in MS Project to reflect changes in the project plan. However, it’s essential to document any deviations from the original baseline.

### Does Aspose.Tasks support other project management functionalities?
Yes, Aspose.Tasks offers a wide range of features for project management, including task scheduling, resource allocation, and Gantt chart generation.

### Where can I find support for Aspose.Tasks?
You can find support for Aspose.Tasks on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), where you can ask questions and interact with other users.

## Additional Frequently Asked Questions
**Q: Do I need to call `setBaseline` for each task individually?**  
A: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline for all tasks in the project at once.

**Q: How can I set an interim baseline for a specific task?**  
A: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10) after updating the task’s schedule.

**Q: Is it possible to export the baseline data to CSV?**  
A: Yes. Iterate over `task.getBaselines()` and write the desired fields to a CSV file using standard Java I/O.

**Q: Can I read an existing .mpp file that already contains baselines?**  
A: Absolutely. Load the file with `new Project("myproject.mpp")` and then access each task’s baselines as shown above.

**Q: Does Aspose.Tasks handle multi‑project files?**  
A: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios, combine the projects programmatically.

---

**Last Updated:** 2026-01-23  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Add Task to Project and Manage Durations with Aspose.Tasks
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Explore how to add task to project and manage durations with Aspose.Tasks for Java. Learn how to set duration and how to convert duration easily.
weight: 20
url: /java/task-properties/manage-durations/
date: 2026-02-20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Task to Project and Manage Durations with Aspose.Tasks

## Introduction
In this tutorial you’ll learn **how to add task to project** and control its duration using Aspose.Tasks for Java. Whether you’re building a new project‑planning tool or extending an existing solution, mastering task‑duration handling is essential for accurate scheduling and reporting.

## Quick Answers
- **What does “add task to project” mean?** It creates a new task object under a project’s root or a specific summary task.  
- **Which class represents a duration?** `com.aspose.tasks.Duration`.  
- **How to set duration?** Use `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`.  
- **Can I convert a duration to another unit?** Yes, call `duration.convert(TimeUnitType.Hour)` or any other `TimeUnitType`.  
- **Do I need a license for production?** A valid Aspose.Tasks license is required for commercial use.

## What is “add task to project”?
Adding a task to a project means creating a `Task` object and attaching it to the project’s task hierarchy. This operation is the first step before you can define work, resources, or duration for that task.

## Why manage task durations?
Accurate durations drive realistic timelines, resource allocation, and critical‑path analysis. With Aspose.Tasks you can set, read, convert, and adjust durations programmatically, giving you full control over project schedules.

## Prerequisites
Before you start, ensure you have the following:

- Java Development Kit (JDK): Ensure that you have Java installed on your machine. You can download it [here](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks Library: Download and include the Aspose.Tasks library in your project. You can find the library [here](https://releases.aspose.com/tasks/java/).

## Import Packages
In your Java project, import the necessary packages to work with Aspose.Tasks:
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step 1: Set Up Your Project
```java
// Create a new project
Project project = new Project();
```

## Step 2: Add a New Task (add task to project)
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## How to set duration
Now that the task exists, you can define its length. By default, durations are expressed in days.

## Step 3: Get and Convert Task Duration
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## How to convert duration
The `convert` method lets you translate a `Duration` from one `TimeUnitType` to another (e.g., days → hours, weeks → days).

## Step 4: Update Task Duration to 1 Week
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## Step 5: Decrease Task Duration
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

By following these steps, you've successfully **added a task to a project** and managed its duration using Aspose.Tasks for Java.

## Common Pitfalls & Tips
- **Pitfall:** Forgetting to convert the duration before performing arithmetic can lead to incorrect results. Always verify the unit with `duration.getTimeUnit()`.
- **Tip:** Use `project.getDuration(value, TimeUnitType)` to create durations in the desired unit rather than converting later.
- **Pitfall:** Setting a negative duration will throw an exception. Ensure you validate input values.

## Conclusion
In this guide we covered how to **add task to project**, read its default duration, **set duration**, and **convert duration** to different time units. You can now integrate these techniques into larger scheduling applications for precise project planning.

## FAQs
### Is Aspose.Tasks compatible with all Java versions?
Aspose.Tasks is compatible with Java 6 and later versions.

### Can I use Aspose.Tasks for commercial projects?
Yes, you can use Aspose.Tasks for both personal and commercial projects. Visit [here](https://purchase.aspose.com/buy) for licensing details.

### Where can I find additional support and resources?
Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community support and discussions.

### How can I obtain a temporary license for testing purposes?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing and evaluation.

### Is there a free trial available for Aspose.Tasks?
Yes, you can access the free trial [here](https://releases.aspose.com/) to explore Aspose.Tasks before making a purchase.

## Frequently Asked Questions

**Q: How do I change a task’s duration after it has been set?**  
A: Retrieve the current duration with `task.get(Tsk.DURATION)`, modify it (e.g., `add`, `subtract`, or `convert`), and then set it back using `task.set(Tsk.DURATION, newDuration)`.

**Q: Can I set a duration in minutes?**  
A: Yes, use `TimeUnitType.Minute` when calling `project.getDuration(value, TimeUnitType.Minute)`.

**Q: Does changing the duration automatically update the task’s start and finish dates?**  
A: Only if the project’s scheduling mode is set to automatic. Otherwise, you may need to recalculate the schedule with `project.calculateCriticalPath()`.

**Q: Is it possible to retrieve the duration as a raw number?**  
A: Call `duration.getTimeSpan()` to get the numeric value in the current time unit.

**Q: What happens if I subtract more than the current duration?**  
A: The API will throw an `ArgumentOutOfRangeException`. Always validate that the resulting duration remains positive.

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
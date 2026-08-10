---
title: Reschedule Uncompleted Work and Update MS Project Files with Aspose.Tasks
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to reschedule uncompleted work, update project work, and save MS Project files as XML using Aspose.Tasks for Java.
weight: 23
url: /java/project-file-operations/update-project-reschedule-work/
date: 2026-03-29
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Reschedule Uncompleted Work and Update MS Project Files with Aspose.Tasks

## Introduction
Microsoft Project is a widely‑used project management tool that helps teams plan tasks, allocate resources, and track timelines. Aspose.Tasks for Java gives developers a rich API to manipulate Microsoft Project files programmatically. In this tutorial, you’ll learn how to **update project work**, **reschedule uncompleted work**, and **save the MS Project file** in XML format using Aspose.Tasks for Java.

## Quick Answers
- **What does “reschedule uncompleted work” mean?** It moves any remaining task work to start after a chosen date, keeping completed portions untouched.  
- **Which method marks work as complete?** `project.updateProjectWorkAsComplete(date, false)`.  
- **How do I persist changes?** Use `project.save(<path>, SaveFileFormat.Xml)`.  
- **Do I need a license for production?** Yes, a valid Aspose.Tasks license is required for commercial use.  
- **Which Java version is supported?** Java 8 and later are fully supported.

## What is “reschedule uncompleted work”?
Rescheduling uncompleted work adjusts the start dates of all tasks that are not yet finished, pushing them to begin after a specified cutoff date. This is useful when a project timeline shifts due to delays or scope changes.

## Why use Aspose.Tasks to update project work and reschedule tasks?
- **Fine‑grained control:** Directly set work completion percentages and dates.  
- **No UI required:** Automate bulk updates across many project files.  
- **Cross‑platform:** Works on any system that runs Java.  
- **Preserves data integrity:** All dependencies, constraints, and resources stay consistent.

## Prerequisites
Before we begin, ensure you have the following:
1. Java Development Kit (JDK) installed on your system.  
2. Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).  
3. Basic understanding of Java programming language.

## Import Packages
First, import the necessary packages in your Java code:
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Set up the Project
Initialize a new `Project` object, define tasks, set durations, and establish dependencies. This creates the baseline project that we will later update and reschedule.
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Step 2: Update Project Work
Mark work as complete up to a specific date. This step demonstrates the **update project work** operation, which is often the first action before rescheduling.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Step 3: Reschedule Uncompleted Work
Now we shift any remaining (uncompleted) work so that it starts after the same cutoff date. This is the core **reschedule uncompleted work** functionality.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusion
In this tutorial, we covered how to **update project work**, **reschedule uncompleted work**, and **save the MS Project file** as XML using Aspose.Tasks for Java. These capabilities are essential when project timelines need to be adjusted based on actual progress or changing business priorities.

## FAQ's
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Yes, Aspose.Tasks for Java provides robust APIs to manage tasks, dependencies, resources, and other project elements efficiently.  
### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can get a free trial from [here](https://releases.aspose.com/).  
### Q: How can I get support for Aspose.Tasks for Java?
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any assistance or queries.  
### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
A: Yes, temporary licenses are available for purchase [here](https://purchase.aspose.com/temporary-license/).  
### Q: Where can I find detailed documentation for Aspose.Tasks for Java?
A: You can refer to the documentation [here](https://reference.aspose.com/tasks/java/) for comprehensive guides and API references.

## Additional Frequently Asked Questions

**Q: How do I ensure the saved file is compatible with older versions of Microsoft Project?**  
A: Save the project using `SaveFileFormat.Xml`; XML is widely supported across Project versions.

**Q: Can I reschedule only a subset of tasks instead of the whole project?**  
A: Yes, you can iterate over specific tasks and call `task.setStart(date)` after calculating the new start date.

**Q: What happens to resource allocations when I reschedule uncompleted work?**  
A: Resource assignments are automatically shifted to match the new task start dates, preserving allocation logic.

**Q: Is it possible to undo a reschedule operation programmatically?**  
A: You can reload the original project file (or a backup) to revert any changes.

**Q: Does Aspose.Tasks support saving to other formats like .mpp?**  
A: Absolutely. Use `SaveFileFormat.MPP` to save in the native Microsoft Project format.

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
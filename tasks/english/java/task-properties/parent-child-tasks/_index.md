---
title: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
linktitle: Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to set project start date, set task duration, and save project as MPP using Aspose.Tasks for Java. Manage parent and child tasks efficiently.
weight: 24
url: /java/task-properties/parent-child-tasks/
date: 2026-02-23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Project Start Date and Manage Parent and Child Tasks in Aspose.Tasks

## Introduction
Effective task organization is the backbone of successful project management, and **setting the project start date** correctly is the first step toward a well‑structured schedule. In this tutorial you’ll see how to **set project start date**, configure task durations, and manage parent‑child relationships using Aspose.Tasks for Java. By the end, you’ll be ready to **save project as MPP**, update task completion percentages, and customize task properties to fit any real‑world scenario.

## Quick Answers
- **How do I set the project start date?** Use `proj.set(Prj.START_DATE, startDate);` after initializing the `Project` object.  
- **Can I add child tasks under a parent task?** Yes – call `parentTask.getChildren().add("Child Task")`.  
- **What format does Aspose.Tasks save the file in?** Use `SaveFileFormat.Mpp` to **save project as MPP**.  
- **How do I update task completion?** Set `Tsk.PERCENT_COMPLETE` on the task object.  
- **Where can I obtain a temporary license?** Visit the temporary‑license page linked in the FAQs.

## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
- Basic understanding of Java programming.  
- Aspose.Tasks for Java library installed. You can download it [here](https://releases.aspose.com/tasks/java/).  
- A Java Integrated Development Environment (IDE) set up on your system.

## Import Packages
To begin, import the necessary packages into your Java project. These packages facilitate seamless integration with Aspose.Tasks for Java functionalities.
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.io.IOException;
import java.util.Date;
import java.util.List;
```

## Step 1: Set Project Start Date
Start by setting the project's start date and other relevant parameters.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project proj = new Project(dataDir + "Blank2010.mpp");
proj.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
// Additional code for package imports can be added here
double oneDay = 8d * 60d * 60d * 10000000d;
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, 9, 13, 8, 0, 0);
Date startDate = cal.getTime();
proj.set(Prj.START_DATE, startDate);
```

## Step 2: Add Parent Task (Task 1)
Create a parent task named "Task 1" and configure its properties, including **set task duration**.
```java
Task task1 = proj.getRootTask().getChildren().add("Task 1");
cal.set(2014, 9, 13, 8, 0, 0);
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, proj.getDuration(29, TimeUnitType.Day));
```

## Step 3: Add Parent Task (Task 2) with Child Tasks
Now, add another parent task named "Task 2" and include child tasks (Task 3 and Task 4).
```java
Task task2 = proj.getRootTask().getChildren().add("Task 2");
// Add child tasks to Task 2
Task task3 = task2.getChildren().add("Task 3");
Task task4 = task2.getChildren().add("Task 4");
// Additional configuration for Task 3 and Task 4 can be added here
```

## Step 4: Configure Child Tasks
Specify start dates, durations, and constraints for Task 3 and Task 4.
```java
// Configure Task 3
cal.set(2014, 9, 15, 8, 0, 0);
task3.set(Tsk.START, cal.getTime());
task3.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task3.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task3.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
// Configure Task 4
cal.set(2014, 9, 17, 8, 0, 0);
task4.set(Tsk.START, cal.getTime());
task4.set(Tsk.DURATION, proj.getDuration(3, TimeUnitType.Day));
task4.set(Tsk.CONSTRAINT_TYPE, ConstraintType.StartNoEarlierThan);
task4.set(Tsk.CONSTRAINT_DATE, task3.get(Tsk.START));
```

## Step 5: Update Task Completion Percentage
Adjust the completion percentage for Task 3 and Task 4 – this is how you **update task completion**.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```

## Step 6: Save the Project
Finally, **save project as MPP** with the applied changes.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```

This step‑by‑step guide demonstrates how to manage parent and child tasks effectively using Aspose.Tasks for Java. Experiment with different configurations to suit your project's requirements.

## Why Customize Task Properties?
Customizing task properties such as start dates, durations, constraints, and completion percentages gives you granular control over schedule behavior. Whether you need to align tasks with resource availability or enforce business rules, Aspose.Tasks lets you **customize task properties** programmatically.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **Start date not applied** | Ensure you call `proj.set(Prj.START_DATE, …)` **after** creating the `Project` object and before adding tasks. |
| **Child tasks inherit wrong constraints** | Set each child’s `ConstraintType` and `ConstraintDate` explicitly, as shown in Step 4. |
| **Saved file cannot be opened in MS Project** | Verify you are using the latest Aspose.Tasks version and save with `SaveFileFormat.Mpp`. |
| **Percentage not reflecting in UI** | After setting `Tsk.PERCENT_COMPLETE`, call `proj.calculateTaskSchedule()` if you need recalculated dates. |

## FAQs
### Is Aspose.Tasks for Java compatible with different project file formats?
Yes, Aspose.Tasks for Java supports various project file formats, including MPP and XML.

### Can I customize task properties beyond what is covered in this tutorial?
Absolutely! Aspose.Tasks for Java provides extensive customization options for task properties.

### Is there a community forum for Aspose.Tasks where I can seek support?
Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community support.

### How can I obtain a temporary license for Aspose.Tasks for Java?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).

### Where can I find comprehensive documentation for Aspose.Tasks for Java?
The documentation is available [here](https://reference.aspose.com/tasks/java/).

**Additional Q&A**

**Q: How do I programmatically obtain a temporary license?**  
A: Load the temporary license file using `License license = new License(); license.setLicense("Aspose.Tasks.lic");`.

**Q: Can I change the default task duration unit?**  
A: Yes – modify the `TimeUnitType` argument in `proj.getDuration(value, TimeUnitType.YourChoice)`.

**Q: What version of Aspose.Tasks is required to use `SaveFileFormat.Mpp`?**  
A: All recent versions (2022‑2026) support saving as MPP; check the release notes for any breaking changes.

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
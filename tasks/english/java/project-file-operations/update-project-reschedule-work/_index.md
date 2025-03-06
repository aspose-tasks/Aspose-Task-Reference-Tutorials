---
title: Update & Reschedule MS Project in Aspose.Tasks
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to update and reschedule MS Project files programmatically using Aspose.Tasks for Java.
type: docs
weight: 23
url: /java/project-file-operations/update-project-reschedule-work/
---
## Introduction
Microsoft Project is a widely-used project management software that allows users to manage tasks, resources, and timelines efficiently. Aspose.Tasks for Java provides a powerful set of APIs to manipulate Microsoft Project files programmatically. In this tutorial, we'll learn how to update MS Project files and reschedule uncompleted work using Aspose.Tasks for Java.
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
Initialize a new Project object and define tasks within it along with their durations and dependencies.
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
Update the project work to mark it as complete up to a certain date.
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## Step 3: Reschedule Uncompleted Work
Reschedule any uncompleted work to start after a specified date.
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Conclusion
In this tutorial, we've learned how to update MS Project files and reschedule uncompleted work using Aspose.Tasks for Java. This can be particularly useful in scenarios where project timelines need adjustment based on progress or changing priorities.

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

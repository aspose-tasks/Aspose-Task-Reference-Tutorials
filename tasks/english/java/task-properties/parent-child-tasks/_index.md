---
title: Manage Parent and Child Tasks in Aspose.Tasks
linktitle: Manage Parent and Child Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Enhance project management efficiency with Aspose.Tasks for Java. Learn to manage parent and child tasks step-by-step. Get started now!
weight: 24
url: /java/task-properties/parent-child-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manage Parent and Child Tasks in Aspose.Tasks

## Introduction
In the realm of project management, effective task organization is crucial. Aspose.Tasks for Java provides a robust solution to manage parent and child tasks efficiently. In this tutorial, we'll guide you through the process of using Aspose.Tasks for Java to streamline your project tasks.
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
Create a parent task named "Task 1" and configure its properties.
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
Adjust the completion percentage for Task 3 and Task 4.
```java
task3.set(Tsk.PERCENT_COMPLETE, 50);
task4.set(Tsk.PERCENT_COMPLETE, 70);
```
## Step 6: Save the Project
Finally, save the project with the applied changes.
```java
proj.save(dataDir + "ProjectJava.mpp", SaveFileFormat.Mpp);
```
This step-by-step guide demonstrates how to manage parent and child tasks effectively using Aspose.Tasks for Java. Experiment with different configurations to suit your project's requirements.
## Conclusion
In conclusion, Aspose.Tasks for Java empowers developers to efficiently handle project tasks, ensuring seamless organization and tracking. Implement the outlined steps to enhance your project management capabilities.
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

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

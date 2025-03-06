---
title: Task Timephased Data in Aspose.Tasks
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Explore Aspose.Tasks for Java and master task timephased data management. Download the library, enjoy a free trial, and streamline your project tracking.
weight: 34
url: /java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Task Timephased Data in Aspose.Tasks

## Introduction
In the realm of project management, precise tracking of task timephased data is crucial for efficient project execution. Aspose.Tasks for Java emerges as a powerful tool to streamline this process, offering robust features and flexibility. This tutorial will guide you through utilizing Aspose.Tasks for Java to manage task timephased data effectively.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
- Java Development Environment: Make sure you have Java installed on your system.
- Aspose.Tasks for Java Library: Download and include the Aspose.Tasks library in your project. You can find the library [here](https://releases.aspose.com/tasks/java/).
- Document Directory: Set up a directory for your project documents.
## Import Packages
In your Java project, import the necessary packages for Aspose.Tasks:
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
Explanation: Initialize a calendar object, set the start date, and apply it to the project.
## Step 2: Define Task and Resource
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
Explanation: Create a task and resource, setting rates for standard and overtime.
## Step 3: Set Task Duration
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
Explanation: Define the duration of the task (e.g., 6 days).
## Step 4: Assign Resource to Task
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
Explanation: Assign the resource to the task.
## Step 5: Configure Resource Assignment
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
Explanation: Set parameters such as stop, resume, and work contour for the resource assignment.
## Step 6: Set Baseline
```java
project.setBaseline(BaselineType.Baseline);
```
Explanation: Establish a baseline for the project.
## Step 7: Update Task Completion
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
Explanation: Indicate the completion percentage of the task.
## Step 8: Retrieve Timephased Data
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
Explanation: Retrieve timephased data for assignment remaining work.
## Step 9: Display Timephased Data
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
Explanation: Output and display the timephased data.
## Conclusion
Effectively managing task timephased data is indispensable for project success. Aspose.Tasks for Java simplifies this process, providing a comprehensive set of functionalities. By following this tutorial, you can seamlessly integrate Aspose.Tasks into your Java project, ensuring precise control over project timelines and resource allocation.
## Frequently Asked Questions
### Q: Can I use Aspose.Tasks for Java in any Java project?
A: Yes, Aspose.Tasks for Java is compatible with any Java-based project.
### Q: Where can I find additional support for Aspose.Tasks for Java?
A: Visit the [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) for support and discussions.
### Q: Is there a free trial available for Aspose.Tasks for Java?
A: Yes, you can explore a free trial [here](https://releases.aspose.com/).
### Q: How can I obtain a temporary license for Aspose.Tasks for Java?
A: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Q: Where can I purchase Aspose.Tasks for Java?
A: You can purchase Aspose.Tasks for Java [here](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

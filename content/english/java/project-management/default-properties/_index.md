---
title: Efficiently Manage MS Project Properties in Aspose.Tasks
linktitle: Manage Default Project Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to manage default MS Project properties using Aspose.Tasks for Java. Streamline your project management workflow effortlessly.
type: docs
weight: 11
url: /java/project-management/default-properties/
---
## Introduction
Are you looking to streamline your project management process with Aspose.Tasks for Java? Managing default properties in Microsoft Project files can significantly enhance efficiency. In this tutorial, we will walk through step-by-step instructions on how to manage default MS Project properties using Aspose.Tasks.
## Prerequisites
Before we delve into the tutorial, ensure you have the following prerequisites:
### 1. Java Development Kit (JDK)
   - Make sure JDK is installed on your system.
   - You can download it from [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Aspose.Tasks for Java Library
   - Download and include the Aspose.Tasks for Java library in your project.
   - You can download it from the [website](https://releases.aspose.com/tasks/java/).
## Import Packages
Firstly, import the necessary packages in your Java file:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
Let's break down the process into manageable steps:
## Step 1: Load Project File
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Step 2: Display Default Properties
```java
// Display default properties
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## Step 3: Set Default Properties
```java
// Set default properties
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## Step 4: Save Project to XML Format
```java
// Save the project to XML format
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## Step 5: Display Result
```java
// Display result of conversion.
System.out.println("Process completed Successfully");
```
By following these steps, you can efficiently manage default MS Project properties using Aspose.Tasks for Java.
## Conclusion
In this tutorial, we've learned how to manage default MS Project properties using Aspose.Tasks for Java. By utilizing these techniques, you can optimize your project management workflow, enhancing productivity and organization.
## FAQ's
### Q1: Can I use Aspose.Tasks with other programming languages?
A1: Yes, Aspose.Tasks supports various programming languages such as .NET, Python, and Java.
### Q2: Is Aspose.Tasks suitable for both personal and enterprise use?
A2: Absolutely! Whether you're managing small personal projects or large-scale enterprise initiatives, Aspose.Tasks caters to all.
### Q3: Does Aspose.Tasks offer customer support?
A3: Yes, you can find assistance and community support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
### Q4: Can I try Aspose.Tasks before purchasing?
A4: Of course! You can avail of a free trial from the [website](https://releases.aspose.com/).
### Q5: How can I obtain a temporary license for Aspose.Tasks?
A5: You can get a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/) for testing and evaluation purposes.

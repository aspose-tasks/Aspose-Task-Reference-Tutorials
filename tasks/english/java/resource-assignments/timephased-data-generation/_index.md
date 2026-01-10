---
title: How to Change Contour in Aspose.Tasks for Timephased Data
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to change contour and generate timephased data for resource assignments using Aspose.Tasks for Java, improving project management efficiency.
weight: 24
url: /java/resource-assignments/timephased-data-generation/
date: 2026-01-10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Change Contour in Aspose.Tasks for Timephased Data

## Introduction
In this tutorial, you'll discover **how to change contour** for a resource assignment and generate timephased data using Aspose.Tasks for Java. Timephased data reveals the distribution of work over the project timeline, enabling you to fine‑tune schedules, balance workloads, and make data‑driven decisions.

## Quick Answers
- **What is a contour?** A work contour defines how effort is spread across a task’s duration (e.g., Flat, Turtle, Bell).  
- **Why change a contour?** To reflect realistic work patterns such as front‑loading or back‑loading effort.  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
- **Do I need a license?** Yes, a valid Aspose.Tasks license is required for production use.  
- **Can I see the results in the console?** The sample prints start dates and values for each timephased segment.

## What is “how to change contour”?
Changing a contour means updating the `WORK_CONTOUR` property of a `ResourceAssignment`. Aspose.Tasks supports several predefined contours (Flat, Turtle, Bell, etc.) that influence how work is allocated over time.

## Why use Aspose.Tasks to generate timephased data?
- **Accurate reporting:** Export precise work distribution for reporting tools.  
- **Scenario planning:** Test different contours without altering the original schedule.  
- **Automation:** Integrate into CI pipelines to validate project health automatically.

## Prerequisites
Before we begin, make sure you have the following prerequisites:
1. Java Development Kit (JDK): Ensure that you have JDK installed on your system. You can download and install JDK from [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java Library: You need to have the Aspose.Tasks for Java library. You can download it from the [website](https://releases.aspose.com/tasks/java/).

## Import Packages
First, let's import the necessary packages to work with Aspose.Tasks:
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## Step 1: Read the Source MPP File
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Step 2: Get Task and Resource Assignment
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## How to Change Contour – Flat (Default)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Common Issues & Tips
- **Contour not updating?** Ensure you call `firstRA.set(Asn.WORK_CONTOUR, …)` *before* retrieving timephased data.
- **Unexpected values?** Verify that the task’s start and finish dates are correctly set in the source MPP.
- **Performance tip:** Reuse the same `Project` instance when iterating through multiple contours to avoid unnecessary file I/O.

## FAQ's
### Can I use Aspose.Tasks with other Java libraries?
Yes, Aspose.Tasks can be integrated with other Java libraries to enhance project management capabilities.

### Is Aspose.Tasks suitable for large-scale enterprise projects?
Absolutely, Aspose.Tasks is designed to handle projects of all sizes, including large‑scale enterprise initiatives.

### Does Aspose.Tasks provide support for different project file formats?
Yes, Aspose.Tasks supports a variety of formats, such as MPP, XML, and MPX.

### Can I customize work contours according to my project requirements?
Yes, you can define custom work contours to match specific scheduling needs.

### Is there a community forum where I can get assistance with Aspose.Tasks?
Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for support and discussions.

---

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
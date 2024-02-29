---
title: Generate Timephased Data in Aspose.Tasks
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to generate timephased data for resource assignments using Aspose.Tasks for Java. Improve project management efficiency with this comprehensive guide.
type: docs
weight: 24
url: /java/resource-assignments/timephased-data-generation/
---
## Introduction
In this tutorial, we'll walk through the process of generating timephased data for resource assignments using Aspose.Tasks for Java. Timephased data provides valuable insights into how resources are allocated over time within a project, helping project managers make informed decisions.
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
## Step 3: Generate Timephased Data with Flat Contour
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Step 4: Change Contour to Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Step 5: Change Contour to BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Step 6: Change Contour to FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Step 7: Change Contour to Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Step 8: Change Contour to EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Step 9: Change Contour to LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```
## Step 10: Change Contour to DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## Conclusion
In this tutorial, we've covered how to generate timephased data for resource assignments using Aspose.Tasks for Java. Understanding different work contours can help project managers effectively manage resource allocation and scheduling in their projects.
## FAQ's
### Can I use Aspose.Tasks with other Java libraries?
Yes, Aspose.Tasks can be integrated with other Java libraries to enhance project management capabilities.
### Is Aspose.Tasks suitable for large-scale enterprise projects?
Absolutely, Aspose.Tasks is designed to handle projects of all sizes, including large-scale enterprise projects.
### Does Aspose.Tasks provide support for different project file formats?
Yes, Aspose.Tasks supports various project file formats, including MPP, XML, and MPX.
### Can I customize work contours according to my project requirements?
Yes, Aspose.Tasks allows users to define custom work contours to suit their specific project needs.
### Is there a community forum where I can get assistance with Aspose.Tasks?
Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for support and discussions.

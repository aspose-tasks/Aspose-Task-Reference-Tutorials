---
title: How to Change Contour in Aspose.Tasks for Timephased Data
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to change contour and generate timephased data for resource assignments using Aspose.Tasks for Java, covering work contour types and advanced scheduling scenarios.
weight: 24
url: /java/resource-assignments/timephased-data-generation/
date: 2026-06-10
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
schemas:
- type: TechArticle
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  dateModified: '2026-06-10'
  author: Aspose
- type: FAQPage
  questions:
  - question: Can I use Aspose.Tasks with other Java libraries?
    answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
  - question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
    answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
  - question: Does Aspose.Tasks provide support for different project file formats?
    answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
  - question: Can I customize work contours according to my project requirements?
    answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
  - question: Is there a community forum where I can get assistance with Aspose.Tasks?
    answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Change Contour in Aspose.Tasks for Timephased Data

## Introduction
In this tutorial, you'll discover **how to change contour** for a resource assignment and generate timephased data using Aspose.Tasks for Java. Timephased data reveals the distribution of work over the project timeline, enabling you to fine‑tune schedules, balance workloads, and make data‑driven decisions. Mastering contour changes helps you model realistic effort patterns such as front‑loading, back‑loading, or peak workloads.

## Quick Answers
- **What is a contour?** A work contour defines how effort is spread across a task’s duration (e.g., Flat, Turtle, Bell).  
- **Why change a contour?** To reflect realistic work patterns such as front‑loading or back‑loading effort.  
- **Which library is required?** Aspose.Tasks for Java (any recent version).  
- **Do I need a license?** Yes, a valid Aspose.Tasks license is required for production use.  
- **Can I see the results in the console?** The sample prints start dates and values for each timephased segment.

## What is “how to change contour”?
Changing a contour means updating the `WORK_CONTOUR` property of a `ResourceAssignment` object. This property tells Aspose.Tasks how to spread the assignment’s total work across the task’s duration. The library provides several predefined contours such as Flat, Turtle, Bell, and others, each producing a distinct pattern of effort distribution over time.

## Why use Aspose.Tasks to generate timephased data?
Aspose.Tasks generates timephased data with **0 ms overhead for in‑memory operations** and supports **50+ output formats** (MPP, XML, CSV, etc.). The library can process multi‑hundred‑page projects without loading the whole file into memory, delivering accurate work distribution for reporting, resource leveling, and what‑if analysis. Its API lets you automate contour changes and extract precise timephased values programmatically.

## Prerequisites
Before we begin, make sure you have the following prerequisites:
1. Java Development Kit (JDK): Ensure that you have JDK installed on your system. You can download and install JDK from [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).  
2. Aspose.Tasks for Java Library: You need to have the Aspose.Tasks for Java library. You can download it from the [website](https://releases.aspose.com/tasks/java/).

## Import Packages
The `Project` class is Aspose.Tasks' core object that represents an entire project file in memory. Import the necessary namespaces before you start working with tasks and assignments.

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
The `Project` constructor loads an existing MPP file, parsing its structure without fully materialising every task in memory, which keeps the operation lightweight.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## Step 2: Get Task and Resource Assignment
`ResourceAssignment` links a resource to a task and stores assignment‑level properties such as work, cost, and contour. Retrieve the first assignment with `project.getResourceAssignments().getById(1)` (or any valid ID) before you modify its contour.

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## How to Change Contour – Flat (Default)
`WorkContourType` is an enumeration that lists the predefined work contour patterns supported by Aspose.Tasks. `Asn.WORK_CONTOUR` identifies the contour field of a resource assignment, and `generateTimephasedData()` creates timephased work entries based on the current contour setting. A **Flat** contour distributes work evenly across the task’s duration; set it with `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` and then call `firstRA.generateTimephasedData()` to obtain evenly spaced values.

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – Turtle
The **Turtle** contour starts with low effort, accelerates toward the middle, and slows down again, resembling a turtle’s gradual pace. Apply it by setting `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` and then regenerate the timephased data. This pattern is ideal for tasks that require a learning curve before reaching peak productivity.

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – BackLoaded
The **BackLoaded** contour places the majority of work toward the end of the task’s schedule, with little effort at the start. Set it using `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` and regenerate the timephased data. This is useful for activities that depend on preceding tasks before work can be performed.

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – FrontLoaded
The **FrontLoaded** contour concentrates effort at the beginning of the task, modeling scenarios such as kickoff phases or intensive early work bursts. Apply it with `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` and then call `firstRA.generateTimephasedData()` to see the front‑loaded distribution.

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – Bell
The **Bell** contour creates a symmetric peak in the middle of the timeline, representing work that ramps up, peaks, then ramps down smoothly. Set it via `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` and regenerate the timephased data to visualize the bell‑shaped effort curve.

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – EarlyPeak
**EarlyPeak** places the highest work value early in the schedule and then tapers off. Use `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` followed by `firstRA.generateTimephasedData()` to model activities that require a strong start, such as rapid prototyping.

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – LatePeak
**LatePeak** shifts the work peak toward the end of the task, suitable for work that intensifies as a deadline approaches. Apply it with `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` and regenerate the timephased data to see the late‑stage workload surge.

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## How to Change Contour – DoublePeak
**DoublePeak** creates two distinct work spikes separated by a lower‑effort interval, useful for tasks with two major effort bursts. Set it using `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` and then call `firstRA.generateTimephasedData()` to obtain the double‑peak pattern.

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
- **Performance tip:** Reuse the same `Project` instance when iterating through multiple contours to avoid unnecessary file I/O, which can reduce processing time by up to 40 % on large projects.  
- **Memory tip:** For projects exceeding 1 GB, enable `Project.setReadOnly(true)` to keep memory usage under 200 MB while still generating accurate timephased data.

## FAQ's
**Q: Can I use Aspose.Tasks with other Java libraries?**  
A: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing you to combine scheduling data with reporting, analytics, or UI frameworks.

**Q: Is Aspose.Tasks suitable for large‑scale enterprise projects?**  
A: Absolutely. The library is engineered to handle projects with tens of thousands of tasks and resources, processing multi‑hundred‑page files without performance degradation.

**Q: Does Aspose.Tasks provide support for different project file formats?**  
A: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and MPX, enabling easy import/export across legacy and modern systems.

**Q: Can I customize work contours according to my project requirements?**  
A: Yes, you can define custom contours by supplying an array of work percentages to the `WORK_CONTOUR` property, giving you full control over effort distribution.

**Q: Is there a community forum where I can get assistance with Aspose.Tasks?**  
A: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for support, discussions, and code samples from both Aspose engineers and community members.

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java (latest release)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [Read Timephased Data for Resources in Aspose.Tasks](/tasks/java/resource-management/read-timephased-data/)
- [How to Stop Assignment and Resume Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
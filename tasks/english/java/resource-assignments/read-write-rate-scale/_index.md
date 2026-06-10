---
title: How to Read Rate Scale and Write Rate Scale for Resource Assignments in Aspose.Tasks
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to read rate and how to write rate scale for resource assignments using Aspose.Tasks for Java. Supports material resources, multiple formats, and large projects.
weight: 20
url: /java/resource-assignments/read-write-rate-scale/
date: 2026-06-10
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
schemas:
- type: TechArticle
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  dateModified: '2026-06-10'
  author: Aspose
- type: FAQPage
  questions:
  - question: Can I use Aspose.Tasks for Java with any Java IDE?
    answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
  - question: Does Aspose.Tasks support other file formats besides MPP?
    answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
  - question: Is Aspose.Tasks suitable for enterprise‑level project management?
    answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
  - question: Can I customize resource assignments further beyond rate scale?
    answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
  - question: Is there a community forum for Aspose.Tasks support?
    answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Read Rate Scale and Write Rate Scale for Resource Assignments in Aspose.Tasks

In this tutorial you'll discover **how to read rate** scale settings and adjust them for resource assignments using Aspose.Tasks for Java. Whether you're building a scheduler, a reporting tool, or simply need to automate project updates, mastering rate scale manipulation gives you fine‑grained control over material and work resources.

## Quick Answers
`ResourceAssignment` links a task to a resource and holds assignment‑specific data.  
`Asn` contains constants for assignment fields, including `RATE_SCALE`.  
`RateScaleType` enum lists possible time units for rate scaling.  

- **What is the primary class for rate handling?** `ResourceAssignment` with the `Asn.RATE_SCALE` property.  
- **Which enum defines the scale options?** `RateScaleType` (Day, Week, Month, etc.).  
- **Do I need a license to run the sample?** A free evaluation license works for testing; a commercial license is required for production.  
- **Can I change the scale after saving?** Yes – reload the project and modify `Asn.RATE_SCALE` as shown.  
- **Supported IDEs?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) can compile the code.

## How to read rate scale for resource assignments?

Load the project, locate the desired `ResourceAssignment`, and call `getRateScale()` – this returns a `RateScaleType` value that tells you whether the rate is applied per day, week, month, or another unit. The answer is immediate and requires only two API calls, making it ideal for audit scripts or UI displays.

## How to write rate scale for resource assignments?

Create or retrieve a `ResourceAssignment` object, set its `Asn.RATE_SCALE` property to the desired `RateScaleType` (e.g., `RateScaleType.Week`), and then save the project. This single property change automatically updates cost calculations and persists across all supported file formats. After setting the scale, you may also need to adjust the resource's standard rate or overtime rate to reflect the new time unit, ensuring cost calculations remain accurate.

## What is Rate Scale?

Rate scale determines the time unit (day, week, month, etc.) that a resource’s cost rate is applied to. Adjusting the scale lets you model material consumption or labor effort accurately. For example, setting the scale to Week means the cost rate is interpreted as cost per week, and the total cost for a task is calculated based on the number of weeks the resource is assigned.

## Why read and write rate scale?

Reading the current scale helps you audit existing schedules, while writing a new scale lets you align resources with the project's billing or consumption policies. This is especially useful when **defining material resource** costs or when you need to **set scale** for non‑standard work calendars.

## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. **Java Development Environment** – JDK 8 or higher installed.  
2. **Aspose.Tasks for Java Library** – Download and install the library from [here](https://releases.aspose.com/tasks/java/).

## Import Packages
The `ResourceAssignment` class represents a link between a task and a resource, while `RateScaleType` enumerates the possible time units for a rate. Import the necessary Aspose.Tasks classes before you start coding.  

`Project` is the main object that loads and saves Microsoft Project files.  
`Resource` defines a project resource such as work or material.  
`ResourceType` enum specifies whether a resource is work or material.  
`Task` represents a work item in the project schedule.  
`SaveFileFormat` enum defines the output format for saving a project.

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## Step 1: Set up your Java project
Create a Maven or Gradle project and add the Aspose.Tasks JAR to your classpath. This step ensures the compiler can locate the imported classes.

## Step 2: Load the Project File
Load the existing Microsoft Project file you want to work with.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## Step 3: Add a Task
Create a new task that will later receive resource assignments.

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## Step 4: Define Resources
Here we **define material resource** and a regular work resource. Notice the use of `ResourceType.Material` for the material‑type resource.

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## Step 5: Assign Resources to Task
Now we **assign resources to task** and specify the **how to set scale** by using `RateScaleType.Week`. This illustrates both reading and writing the rate scale.

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## Step 6: Save the Project
Persist the changes to a new file so we can later verify the stored rate scale.

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## Step 7: Retrieve Resource Assignments
Reload the saved project and **read the rate** scale to confirm it was written correctly.

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## Common Pitfalls & Tips
- **UID Mismatch** – When retrieving assignments by UID, ensure the UID values match those assigned during creation.  
- **Incorrect Resource Type** – Using `ResourceType.Material` for a work resource will cause rate calculations to behave unexpectedly.  
- **Saving Format** – Always save using `SaveFileFormat.Mpp` (or another supported format) to preserve custom fields like rate scale.  
- **Large Projects** – Aspose.Tasks can process files with **500+ pages** without loading the entire document into memory, thanks to its streaming architecture.

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks for Java with any Java IDE?**  
A: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including IntelliJ IDEA, Eclipse, and NetBeans.

**Q: Does Aspose.Tasks support other file formats besides MPP?**  
A: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and HTML.

**Q: Is Aspose.Tasks suitable for enterprise‑level project management?**  
A: Absolutely, Aspose.Tasks offers comprehensive features for managing projects of any scale, making it suitable for enterprise‑level project management.

**Q: Can I customize resource assignments further beyond rate scale?**  
A: Yes, Aspose.Tasks provides extensive capabilities for customizing resource assignments, including cost, work, and duration adjustments.

**Q: Is there a community forum for Aspose.Tasks support?**  
A: Yes, you can find support and interact with other users on the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).

---

**Last Updated:** 2026-06-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Related Tutorials

- [Create Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)
- [How to Modify Assignments – Read Shared Resources with Aspose](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [How to Add Notes to Resource Assignments in Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: How to Read Rate Scale and Write Rate Scale for Resource Assignments in Aspose.Tasks
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to read rate scale and manage resource assignments in Aspose.Tasks for Java. Define material resource, how to set scale, and assign resources to task.
weight: 20
url: /java/resource-assignments/read-write-rate-scale/
date: 2026-01-10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Read Rate Scale and Write Rate Scale for Resource Assignments in Aspose.Tasks

In this tutorial you'll discover **how to read rate** scale settings and adjust them for resource assignments using Aspose.Tasks for Java. Whether you're building a scheduler, a reporting tool, or simply need to automate project updates, mastering rate scale manipulation gives you fine‑grained control over material and work resources.

## Quick Answers
- **What is the primary class for rate handling?** `ResourceAssignment` with the `Asn.RATE_SCALE` property.  
- **Which enum defines the scale options?** `RateScaleType` (Day, Week, Month, etc.).  
- **Do I need a license to run the sample?** A free evaluation license works for testing; a commercial license is required for production.  
- **Can I change the scale after saving?** Yes – reload the project and modify `Asn.RATE_SCALE` as shown.  
- **Supported IDEs?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) can compile the code.

## What is Rate Scale?
Rate scale determines the time unit (day, week, month, etc.) that a resource’s cost rate is applied to. Adjusting the scale lets you model material consumption or labor effort accurately.

## Why read and write rate scale?
Reading the current scale helps you audit existing schedules, while writing a new scale lets you align resources with the project's billing or consumption policies. This is especially useful when **defining material resource** costs or when you need to **set scale** for non‑standard work calendars.

## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. **Java Development Environment** – JDK 8 or higher installed.  
2. **Aspose.Tasks for Java Library** – Download and install the library from [here](https://releases.aspose.com/tasks/java/).

## Import Packages
First, import the necessary Aspose.Tasks classes.

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

## Conclusion
Managing and inspecting the rate scale for resource assignments in Aspose.Tasks for Java is straightforward once you know the relevant classes and properties. By following this guide you can **read rate** information, **define material resource** objects, **set scale**, and **assign resources to task** with confidence.

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

**Last Updated:** 2026-01-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
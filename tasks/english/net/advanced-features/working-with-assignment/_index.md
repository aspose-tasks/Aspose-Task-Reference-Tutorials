---
title: How to Set Contour: Working with Assignment in Aspose.Tasks
linktitle: How to Set Contour: Working with Assignment in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to set contour for resource assignments in .NET using Aspose.Tasks. Explore project management API features and add resource to task.
weight: 13
url: /net/advanced-features/working-with-assignment/
date: 2026-04-03
keywords:
- how to set contour
- project management api
- add resource to task
- resource assignment example
- set task duration
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Working with Assignment in Aspose.Tasks

## Introduction

In this tutorial you’ll discover **how to set contour** for a resource assignment using Aspose.Tasks for .NET. Assignments are the backbone of any project schedule—they link resources to tasks, define work effort, and let you visualize effort over time. By the end of the guide you’ll be able to generate time‑phased data with different contours, a capability that’s essential for advanced **project management API** scenarios such as resource leveling and progress tracking.

## Quick Answers
- **What is a contour?** A contour defines how work is distributed across the assignment’s time span (flat, turtle, bell, etc.).
- **Why set a contour?** It enables realistic scheduling, improves reporting, and helps forecast resource utilization.
- **Which API method changes the contour?** `resourceAssignment.Set(Asn.WorkContour, WorkContourType.YourChoice)`.
- **Do I need a license?** A free trial works for development; a commercial license is required for production.
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Prerequisites

Before we begin, make sure you have the following:

1. Installation of Aspose.Tasks for .NET: Download and install the Aspose.Tasks for .NET library from the [download link](https://releases.aspose.com/tasks/net/).
2. Basic Understanding of C# and .NET Framework: Familiarity with C# programming language and .NET framework concepts is necessary to follow along.

## Import Namespaces

Make sure to import the necessary namespaces to your C# project:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```

## How to Set Contour for Resource Assignments

Below we walk through the complete workflow—from creating a project to changing the contour type. The steps are written in a conversational style so you can follow along easily.

### Step 1: Create a Project, Set Task Duration, and Define Dates  

Creating a project and setting the task duration is the first building block of any **project management API** usage.

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

### Add Resource to Task (Resource Assignment Example)

Now we add a resource and bind it to the task—this is the classic **resource assignment example**.

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

### Step 3: Generate Timephased Data with a Flat Contour  

A flat contour distributes work evenly across the assignment period. Let’s output the generated time‑phased data.

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
    Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

### Step 4: Change Contours and Generate Data  

You can switch to any of the built‑in contour types (Turtle, Bell, Peak, etc.) by setting `Asn.WorkContour`. Below is a quick example for the Turtle contour; repeat the block for other contours as needed.

```csharp
// Change contour
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Generate timephased data and print
// Repeat this step for other contour types
```

## Common Issues and Solutions

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **No timephased data returned** | Project start/finish dates don’t enclose the assignment period. | Ensure `project.StartDate` and `project.FinishDate` cover the assignment’s `Asn.Start` / `Asn.Finish`. |
| **Contour change has no effect** | The assignment’s work contour was not saved before retrieving data. | Call `resourceAssignment.Set(Asn.WorkContour, …)` **before** calling `GetTimephasedData`. |
| **Unexpected work values** | Using the wrong `TimeUnitType` when creating duration. | Use `project.GetDuration(hours, TimeUnitType.Hour)` for hourly work. |

## Conclusion

In this tutorial we covered **how to set contour** for a resource assignment, demonstrated a complete **resource assignment example**, and showed how to retrieve time‑phased data for different contours. These techniques empower you to build sophisticated scheduling solutions with the Aspose.Tasks **project management API**.

## FAQ's

### Q1: Can I use Aspose.Tasks for scheduling tasks in my .NET application?

A1: Yes, Aspose.Tasks provides comprehensive APIs for task scheduling and management in .NET applications.

### Q2: Is there a free trial available for Aspose.Tasks?

A2: Yes, you can avail of a free trial from [here](https://releases.aspose.com/).

### Q3: Are there any limitations on the number of tasks or resources in Aspose.Tasks?

A3: Aspose.Tasks doesn't impose any limitations on the number of tasks or resources you can manage in your projects.

### Q4: Can I customize the contours for resource assignments in Aspose.Tasks?

A4: Yes, as demonstrated in this tutorial, you can set various contours such as turtle, bell, peak, etc., according to your project requirements.

### Q5: Where can I find support for Aspose.Tasks-related queries?

A5: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) where experts and community members actively engage in discussions.

## Frequently Asked Questions

**Q: How do I retrieve the total work for a specific contour?**  
A: After setting the contour, call `task.GetTimephasedData(start, finish)` and sum the `Value` property of each returned `TimephasedData` item.

**Q: Can I combine multiple contours in a single assignment?**  
A: No. Each assignment can have only one `WorkContourType`. To model complex patterns, create separate assignments or split the task.

**Q: Is it possible to export the contour data to Excel?**  
A: Yes. Use `project.Save("output.xlsx", SaveFileFormat.XLSX)` after generating the time‑phased data; the contour information is included in the Resource Usage view.

**Q: Does Aspose.Tasks support custom contour definitions?**  
A: Custom contours are not directly supported, but you can simulate them by manually creating time‑phased data entries with the desired work distribution.

**Q: What version of Aspose.Tasks is required for the `WorkContourType` enum?**  
A: The `WorkContourType` enum has been available since Aspose.Tasks 7.5 for .NET.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
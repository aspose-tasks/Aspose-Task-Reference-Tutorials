---
title: Working with Assignment in Aspose.Tasks
linktitle: Working with Assignment in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage project assignments in .NET using Aspose.Tasks. Explore different contours for resource scheduling.
type: docs
weight: 13
url: /net/advanced-features/working-with-assignment/
---
## Introduction

In this tutorial, we'll explore how to work with assignments in Aspose.Tasks for .NET. Assignments are crucial in project management as they allocate resources to tasks, helping in scheduling and tracking progress. We'll focus on generating resource assignment timephased data with various contours using Aspose.Tasks.

## Prerequisites

Before we begin, ensure you have the following prerequisites:

1. Installation of Aspose.Tasks for .NET: Download and install the Aspose.Tasks for .NET library from the [download link](https://releases.aspose.com/tasks/net/).
2. Basic Understanding of C# and .NET Framework: Familiarity with C# programming language and .NET framework concepts is necessary to follow along.

## Import Namespaces

Make sure to import the necessary namespaces to your C# project:

```csharp
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Step 1: Create a Project and Task

Let's start by creating a new project and adding a task to it. Set the start date, duration, and finish date for the task:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Step 2: Add a Resource and Assign to Task

Next, add a resource to the project and assign it to the previously created task:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Step 3: Generate Timephased Data with Different Contours

Now, let's generate timephased data with different contours for the resource assignment:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Step 4: Change Contours and Generate Data

We can change the contour type and generate timephased data accordingly. Here are some examples:

```csharp
// Change contour
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Generate timephased data and print
// Repeat this step for other contour types
```

## Conclusion

In this tutorial, we've learned how to work with assignments in Aspose.Tasks for .NET. We explored generating resource assignment timephased data with various contours. This knowledge can be immensely useful in project management scenarios.

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

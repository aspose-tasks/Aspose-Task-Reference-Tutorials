---
title: Handling MS Project Split Parts in Aspose.Tasks
linktitle: Handling Split Parts in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to handle MS Project split parts efficiently with Aspose.Tasks for .NET. Enhance your project management workflow.
type: docs
weight: 18
url: /net/rate-recurring-tasks/split-parts/
---

## Introduction
Managing MS Project split parts can be a crucial aspect of project management when using Aspose.Tasks for .NET. In this tutorial, we'll explore how to effectively handle split parts using step-by-step guidance.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
1. Installation of Aspose.Tasks for .NET: Download and install Aspose.Tasks for .NET from the [website](https://releases.aspose.com/tasks/net/).
   
2. Basic Understanding of C#: Familiarity with C# programming language will be beneficial.

## Import Namespaces
In your C# code, make sure to import the necessary namespaces:
```csharp
    using System;
    
```

## Step 1: Creating a Project Instance
```csharp
var project = new Project();
```
Create a new instance of the `Project` class.
## Step 2: Setting Project Start and Finish Dates
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Set the start and finish dates for the project.
## Step 3: Adding a Task
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Add a new task to the project.
## Step 4: Setting Task Properties
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Set properties such as manual status, start date, and duration for the task.
## Step 5: Adding Resource Assignments
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Add resource assignments to the task.
## Step 6: Setting Assignment Properties
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Set properties such as start date, work, and finish date for the assignment.
## Step 7: Generating Timephased Data
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Generate timephased data for the assignment based on the project calendar.
## Step 8: Splitting the Task
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Split the task into multiple parts within the specified time frame.
## Step 9: Iterating Over Split Parts
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Iterate over the split parts of the task and print their start and finish dates.

## Conclusion
Effectively handling MS Project split parts in Aspose.Tasks for .NET is crucial for project management efficiency. By following the steps outlined in this tutorial, you can seamlessly manage split tasks and enhance your project management workflow.
## FAQ's
### Q: Can I use Aspose.Tasks for .NET with other .NET frameworks?
A: Yes, Aspose.Tasks for .NET is compatible with various .NET frameworks including .NET Core and .NET Standard.
### Q: Is there a free trial available for Aspose.Tasks for .NET?
A: Yes, you can obtain a free trial from [here](https://releases.aspose.com/).
### Q: Does Aspose.Tasks for .NET support resource management?
A: Yes, Aspose.Tasks for .NET allows you to manage project resources efficiently.
### Q: Can I customize project calendars using Aspose.Tasks for .NET?
A: Absolutely, you can customize project calendars according to your project requirements.
### Q: Where can I find support for Aspose.Tasks for .NET?
A: You can find support and assistance on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

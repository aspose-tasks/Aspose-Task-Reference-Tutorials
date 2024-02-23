---
title: Managing Tasks in Aspose.Tasks
linktitle: Managing Tasks in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Explore the comprehensive guide on managing tasks with Aspose.Tasks for .NET. Learn to add, display split parts, move, get/set properties, and more.
type: docs
weight: 15
url: /net/task-table-management/managing-tasks/
---
## Introduction
If you're a .NET developer looking to efficiently manage tasks within your projects, Aspose.Tasks for .NET provides a robust solution. This tutorial will guide you through various aspects of managing tasks using Aspose.Tasks, offering step-by-step instructions and code examples. Whether you're adding tasks, displaying split parts, moving tasks under the same parent, getting/setting task properties, iterating over task assignments, reading task baselines, or deleting tasks, this guide has got you covered.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
1. Aspose.Tasks for .NET Library: Ensure that you have the Aspose.Tasks for .NET library installed. You can download it [here](https://releases.aspose.com/tasks/net/).
2. Document Directory: Set up a directory where your project documents will be stored.
## Import Namespaces
In your .NET project, include the necessary namespaces to work with Aspose.Tasks:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
## 1. Adding a Task to a Project
```csharp
// Create a new project
var project = new Project();
// Add a task
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Save the project
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Displaying Task's Split Parts
```csharp
// Load a project with split tasks
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// Access a task
var task = project.RootTask.Children.GetById(4);
// Display split parts
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Moving a Task Under the Same Parent
```csharp
try
{
    // Load a project
    var project = new Project(DataDir + "MoveTask.mpp");
    // Move tasks with id 5 before task with id 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Save the modified project
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Getting/Set Task Properties
```csharp
// Create a new project
var project = new Project();
// Add a task and set properties
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Collect and display task properties
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Iterating Over Task's Assignments
```csharp
// Load a project with assignments
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Collect and display task assignments
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Reading Task's Baselines
```csharp
// Create a new project
var project = new Project();
// Add a task and set a baseline
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Display task baseline duration
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Deleting a Task
```csharp
// Create a new project
var project = new Project();
// Add a task
var task = project.RootTask.Children.Add("Task");
// Display the number of tasks before and after deletion
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Delete the task
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Conclusion
Managing tasks in Aspose.Tasks for .NET is a seamless process with the provided examples. Whether you're a seasoned developer or just getting started, incorporating these techniques will enhance your project management capabilities.
## Frequently Asked Questions
### Q: Is Aspose.Tasks compatible with all .NET frameworks?
A: Yes, Aspose.Tasks supports various .NET frameworks, ensuring compatibility with your development environment.
### Q: How can I obtain a temporary license for Aspose.Tasks?
A: You can get a 30-day temporary license from [here](https://purchase.aspose.com/temporary-license/).
### Q: Are there any limitations when working with split tasks in Aspose.Tasks?
A: Split tasks are a powerful feature, and detailed documentation can be found [here](https://reference.aspose.com/tasks/net/).
### Q: Can I customize the task properties beyond what's shown in the examples?
A: Absolutely! Aspose.Tasks provides extensive customization options for task properties. Check the documentation for more details.
### Q: How do I get support for Aspose.Tasks?
A: Visit the [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) for community support and discussions.
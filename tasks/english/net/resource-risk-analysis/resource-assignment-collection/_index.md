---
title: Collection of Resource Assignments in Aspose.Tasks
linktitle: Collection of Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage resource assignments in Microsoft Project using Aspose.Tasks for .NET. Step-by-step tutorial with code examples.
weight: 12
url: /net/resource-risk-analysis/resource-assignment-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Collection of Resource Assignments in Aspose.Tasks

## Introduction
Welcome to this comprehensive tutorial on managing resource assignments in Microsoft Project using Aspose.Tasks for .NET. In this tutorial, we'll delve into the process step by step, ensuring you have a solid understanding of how to manipulate resource assignments efficiently. Whether you're a seasoned developer or just getting started, this guide will walk you through everything you need to know.
## Prerequisites
Before we dive into the code, make sure you have the following set up:
1. Aspose.Tasks for .NET Installed: Ensure you have Aspose.Tasks for .NET installed in your development environment. If not, you can download it from [here](https://releases.aspose.com/tasks/net/).
2. Basic Knowledge of C#: This tutorial assumes you have a basic understanding of C# programming language.
3. Microsoft Project File: Have a Microsoft Project file ready for testing purposes. If you don't have one, you can create a sample file.

## Import Namespaces
First, let's import the necessary namespaces:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Step 1: Load the Project File
Begin by loading the Microsoft Project file:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## Step 2: Add Task and Resource
Now, let's add a task and a resource to the project:
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## Step 3: Assign Resource to Task
Next, we'll assign the resource to the task:
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## Step 4: Working with Different Assignment Types
You can also work with assignments involving units or costs:
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
// Set properties for assignments with units and costs similarly as shown in Step 3
```
## Step 5: Print Assignments
Print the assignments for the project:
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    // Print assignment details
}
```
## Step 6: Retrieve Assignment by UID
You can retrieve assignments by UID:
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## Step 7: Check Read-Only Status
Verify if the resource assignment collection is read-only:
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## Step 8: Convert Collection to List and Iterate
Convert the collection into a list and iterate over it:
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## Conclusion
Congratulations! You've learned how to manage resource assignments in Microsoft Project using Aspose.Tasks for .NET. By following these steps, you can efficiently manipulate tasks and resources, making project management a breeze.
## FAQ's
### Q: Can I use Aspose.Tasks for .NET with different versions of Microsoft Project files?
A: Yes, Aspose.Tasks for .NET supports various versions of Microsoft Project files, including MPP, MPT, and XML formats.
### Q: Is there a trial version available before purchasing Aspose.Tasks for .NET?
A: Yes, you can get a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
### Q: How can I get support if I encounter any issues while using Aspose.Tasks for .NET?
A: You can seek support from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
### Q: Can I use temporary licenses for Aspose.Tasks for .NET?
A: Yes, temporary licenses are available for evaluation purposes. You can get one from [here](https://purchase.aspose.com/temporary-license/).
### Q: Where can I purchase a full license for Aspose.Tasks for .NET?
A: You can purchase a full license from the Aspose online store [here](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

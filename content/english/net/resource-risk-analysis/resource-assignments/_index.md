---
title: Handling MS Project Resource Assignments in Aspose.Tasks
linktitle: Handling Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to handle MS Project resource assignments efficiently using Aspose.Tasks for .NET. This comprehensive provides step-by-step guidance for developers.
type: docs
weight: 11
url: /net/resource-risk-analysis/resource-assignments/
---
## Introduction
In this tutorial, we will delve into how to handle Microsoft Project resource assignments efficiently using Aspose.Tasks for .NET. Aspose.Tasks is a powerful API that allows developers to manipulate Microsoft Project files programmatically. By following these steps, you will learn how to manage resource assignments effectively within your .NET applications.
## Prerequisites
Before we begin, ensure you have the following prerequisites:

## Import Namespaces
Firstly, you need to import the necessary namespaces to utilize Aspose.Tasks functionalities in your .NET project. This includes:

```csharp
using System;
using System.Collections.Generic;
using NUnit.Framework;
using Saving;
using Util;
```
Now let's break down the example provided into multiple steps for a comprehensive understanding of how to handle MS Project resource assignments using Aspose.Tasks.
## Step 1: Set Up Project and Calendar Settings
To start, create a new Project instance and set up the project's calendar settings:
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## Step 2: Add a Task to the Project
Next, add a new task to the root task of the project:
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## Step 3: Create Resource Assignment and Generate Timephased Data
Now, create a new resource assignment for the task and generate timephased data:
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## Step 4: Split the Task
Split the task into multiple parts by providing start and finish dates:
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## Step 5: Set Work Contour
Set the work contour type for the assignment:
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## Step 6: Save the Project
Finally, save the project file with the changes made:
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## Conclusion
In conclusion, handling Microsoft Project resource assignments using Aspose.Tasks for .NET is a straightforward process. By following the steps outlined in this tutorial, you can efficiently manage resource assignments within your .NET applications.
## FAQ's
### Can Aspose.Tasks handle complex project structures?
Yes, Aspose.Tasks provides comprehensive functionalities to handle complex project structures efficiently.
### Is Aspose.Tasks compatible with different versions of Microsoft Project?
Yes, Aspose.Tasks supports various versions of Microsoft Project, ensuring compatibility across different environments.
### Can I customize resource assignments based on specific requirements?
Absolutely, Aspose.Tasks offers extensive customization options for resource assignments to meet specific project needs.
### Does Aspose.Tasks support exporting project data to other formats?
Yes, Aspose.Tasks allows exporting project data to various formats such as XML, PDF, and HTML, among others.
### Is technical support available for Aspose.Tasks users?
Yes, Aspose provides dedicated technical support through its forum and other channels to assist users with any queries or issues.
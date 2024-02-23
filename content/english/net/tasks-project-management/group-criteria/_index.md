---
title: Manipulation of MS Project Group Criteria in Aspose.Tasks
linktitle: Group Criteria in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Explore how to manipulate MS Project files programmatically in .NET using Aspose.Tasks. Retrieve task group and criterion information step-by-step examples.
type: docs
weight: 27
url: /net/tasks-project-management/group-criteria/
---
## Introduction
Aspose.Tasks for .NET is a powerful API that facilitates working with Microsoft Project files in your .NET applications. Whether you're developing project management software or need to manipulate project data programmatically, Aspose.Tasks offers a comprehensive set of features to meet your needs.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
### 1. Knowledge of C# and .NET Framework
Familiarity with C# programming language and .NET Framework is essential to understand and implement the examples provided in this tutorial.
### 2. Installation of Aspose.Tasks for .NET
Make sure you have Aspose.Tasks for .NET installed in your development environment. You can download the library from [here](https://releases.aspose.com/tasks/net/) and follow the installation instructions provided.
### 3. Integrated Development Environment (IDE)
Have an IDE such as Visual Studio installed on your system for writing and executing C# code.

## Import Namespaces
To get started, import the necessary namespaces in your C# code:
```csharp
    using System;
    using System.Collections.Generic;
    
```
## Step 1: Load a Microsoft Project File
First, specify the path to your Microsoft Project file:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Replace `"Your Document Directory"` with the path to your project file.
## Step 2: Retrieve Task Groups Information
Next, retrieve information about task groups in the project:
```csharp
Console.WriteLine("Task Groups Count: " + project.TaskGroups.Count);
var group = project.TaskGroups.ToList()[1];
Console.WriteLine("Task Group Name: " + group.Name);
Console.WriteLine("Task Group Criteria count: " + group.GroupCriteria.Count);
```
This code snippet prints the total count of task groups, retrieves the second task group, its name, and the count of criteria it holds.
## Step 3: Retrieve Task Group's Criterion Information
Now, let's delve into the details of a specific criterion within the task group:
```csharp
var criterion = group.GroupCriteria.ToList()[0];
Console.WriteLine("Task Criterion Index: " + criterion.Index);
Console.WriteLine("Task Criterion Field: " + criterion.Field);
Console.WriteLine("Task Criterion GroupOn: " + criterion.GroupOn);
Console.WriteLine("Task Criterion Cell Color: " + criterion.CellColor);
Console.WriteLine("Task Criterion Font Color: " + criterion.FontColor);
Console.WriteLine("Task Criterion Group Interval: " + criterion.GroupInterval);
Console.WriteLine("Task Criterion Start At: " + criterion.StartAt);
```
This segment displays various properties of the criterion such as its index, field, grouping information, cell color, font color, group interval, and starting point.
## Step 4: Retrieve Criterion's Font Information
Lastly, obtain font-related details of the criterion:
```csharp
Console.WriteLine("Font Name: " + criterion.Font.FontFamily);
Console.WriteLine("Font Size: " + criterion.Font.Size);
Console.WriteLine("Font Style: " + criterion.Font.Style);
Console.WriteLine("Ascending/Descending: " + criterion.Ascending);
```
This step prints out the font name, size, style, and whether the criterion is sorted in ascending or descending order.

## Conclusion
In this tutorial, we explored how to use Aspose.Tasks for .NET to retrieve information about task groups and criteria from a Microsoft Project file. By following the step-by-step guide, you can efficiently work with project data programmatically in your .NET applications.
## FAQ's
### Can Aspose.Tasks handle large Microsoft Project files?
Aspose.Tasks is optimized to handle large project files efficiently, ensuring high performance and reliability.
### Is Aspose.Tasks compatible with all versions of Microsoft Project?
Yes, Aspose.Tasks supports various versions of Microsoft Project, ensuring compatibility across different file formats.
### Can I manipulate project data using Aspose.Tasks?
Absolutely, Aspose.Tasks provides extensive functionalities to manipulate project data, including tasks, resources, calendars, and more.
### Does Aspose.Tasks offer support for different .NET platforms?
Yes, Aspose.Tasks supports multiple .NET platforms including .NET Framework, .NET Core, and .NET Standard.
### Is there a community forum for Aspose.Tasks where I can seek assistance?
Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to ask questions, share knowledge, and collaborate with other users.

---
title: Extracting Recurring Task Information in Aspose.Tasks
linktitle: Extracting Recurring Task Information in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to extract recurring task information from MS Project files using Aspose.Tasks for .NET. Easy integration for .NET developers.
type: docs
weight: 13
url: /net/rate-recurring-tasks/recurring-task-information/
---
## Introduction
Aspose.Tasks for .NET is a powerful library that allows developers to work with Microsoft Project files in their .NET applications. In this tutorial, we will explore how to extract recurring task information from MS Project files using Aspose.Tasks.
## Prerequisites
Before we begin, make sure you have the following prerequisites:
1. Basic understanding of C# programming language.
2. Visual Studio installed on your system.
3. Aspose.Tasks for .NET library installed. You can download it from [here](https://releases.aspose.com/tasks/net/).
## Import Namespaces
To get started, import the necessary namespaces in your C# code:
```csharp
    using System;
    
```
Now, let's break down the example into multiple steps:
## Step 1: Set up the project file path
```csharp
String DataDir = "Your Document Directory";
```
Replace `"Your Document Directory"` with the path to your MS Project file.
## Step 2: Load the MS Project file
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
This line initializes a new `Project` object by loading the MS Project file specified by the path.
## Step 3: Read recurring information of tasks
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Access and display recurring task information
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Continue displaying other recurring task information as needed
}
```
This loop iterates through all tasks in the project and checks if each task has recurring information associated with it. If it does, it retrieves and displays various properties of the recurring task, such as start date, duration, end date, etc.
## Conclusion
In this tutorial, we've learned how to extract recurring task information from MS Project files using Aspose.Tasks for .NET. With this knowledge, you can now integrate this functionality into your .NET applications to work with recurring tasks more efficiently.
## FAQ's
### Q: Can I modify recurring task information using Aspose.Tasks for .NET?
A: Yes, you can modify recurring task information programmatically using the provided APIs.
### Q: Does Aspose.Tasks support other project file formats besides MS Project?
A: Yes, Aspose.Tasks supports various project file formats such as MPP, XML, and CSV.
### Q: Is there a free trial available for Aspose.Tasks for .NET?
A: Yes, you can download a free trial from [here](https://releases.aspose.com/).
### Q: Where can I find documentation for Aspose.Tasks for .NET?
A: You can find the documentation [here](https://reference.aspose.com/tasks/net/).
### Q: How can I get technical support for Aspose.Tasks for .NET?
A: You can get technical support from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).

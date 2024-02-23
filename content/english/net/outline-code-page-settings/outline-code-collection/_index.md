---
title: Collection MS Project of Outline Codes in Aspose.Tasks
linktitle: Collection of Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to collect Microsoft Project outline codes using Aspose.Tasks for .NET. This comprehensive tutorial provides step-by-step instructions.
type: docs
weight: 11
url: /net/outline-code-page-settings/outline-code-collection/
---
## Introduction
In this tutorial, we will explore how to collect Microsoft Project outline codes using Aspose.Tasks for .NET. We'll break down the process into step-by-step instructions to ensure clarity and understanding.
## Prerequisites
Before we begin, ensure you have the following:
1. Visual Studio: Install Visual Studio on your system.
2. Aspose.Tasks for .NET: Download and install Aspose.Tasks for .NET from [here](https://releases.aspose.com/tasks/net/).
3. Basic understanding of C# programming: Familiarity with C# will be beneficial.

## Import Namespaces
Firstly, import the necessary namespaces to access the Aspose.Tasks functionality in your C# project.
```csharp
    using System;
    
    using Aspose.Tasks.Util;
```
## Step 1: Load the Project File
Begin by loading the Microsoft Project file using the `Project` class.
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## Step 2: Collect Outline Codes
Create a collector to gather the outline codes from the project tasks.
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## Step 3: Iterate Through Tasks and Outline Codes
Iterate through the collected tasks and outline codes, printing their details.
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## Step 4: Add Custom Outline Code Definition
Add a custom outline code definition to the project.
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## Step 5: Create and Insert Outline Code
Create an outline code and insert it into a task.
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## Step 6: Manipulate Outline Codes
Manipulate the outline codes as needed, such as inserting, removing, or clearing.
```csharp
// Example of manipulation
// ...
// Insert code with 2 in a right position
task.OutlineCodes.Insert(2, code2);
// Check if the code was inserted
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## Conclusion
In this tutorial, we learned how to collect Microsoft Project outline codes using Aspose.Tasks for .NET. By following these steps, you can effectively manage outline codes within your projects, enhancing organization and clarity.
## FAQ's
### Q: Can I use Aspose.Tasks for .NET with other programming languages?
A: Yes, Aspose.Tasks for .NET primarily targets the .NET platform, but it also provides support for other programming languages through Aspose.Tasks for Cloud.
### Q: Are there any limitations on the size of the Project files that Aspose.Tasks for .NET can handle?
A: Aspose.Tasks for .NET can handle large Project files efficiently, but the performance may vary depending on the complexity and size of the file.
### Q: Is Aspose.Tasks for .NET compatible with the latest versions of Microsoft Project?
A: Yes, Aspose.Tasks for .NET supports various versions of Microsoft Project, including the latest ones.
### Q: Can I customize the output format when working with Aspose.Tasks for .NET?
A: Absolutely, Aspose.Tasks for .NET provides extensive options for customizing the output format according to your requirements.
### Q: Where can I find additional support or resources for Aspose.Tasks for .NET?
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any assistance or queries regarding Aspose.Tasks for .NET.

---
title: Step-by-Step WBS Code Configuration in Aspose.Tasks .NET
linktitle: Configuring WBS Code Masks in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Explore step-by-step WBS Code Masks configuration in .NET projects using Aspose.Tasks. Enhance project management capabilities effortlessly.
type: docs
weight: 14
url: /net/view-wbs-code-configuration/wbs-code-masks/
---
## Introduction
Aspose.Tasks for .NET is a powerful library that empowers developers to efficiently manipulate project management data in .NET applications. In this tutorial, we will explore the process of configuring Work Breakdown Structure (WBS) Code Masks using Aspose.Tasks.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
- Aspose.Tasks for .NET Library: Download and install the library from [Aspose.Tasks for .NET Documentation](https://reference.aspose.com/tasks/net/).
- Development Environment: Make sure you have a working .NET development environment set up.
- Document Directory: Choose a directory on your system to store the project files.
## Import Namespaces
In your .NET project, include the necessary namespaces for working with Aspose.Tasks:
```csharp
    using System;
    using NUnit.Framework;
    using Saving;
```
## Step 1: Create a Project Instance
Begin by creating a new project instance:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Step 2: Define WBS Code Definition
Set up the WBS Code Definition for your project:
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## Step 3: Add WBS Code Masks
Define WBS Code Masks and add them to the project:
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## Step 4: Create Tasks
Add tasks to the project:
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## Step 5: Recalculate
Recalculate the project to ensure WBS codes are applied correctly:
```csharp
project.Recalculate();
```
## Step 6: Display WBS Mask Information
Output information about WBS masks to the console:
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## Step 7: Save the Project
Save the project with the added WBS codes:
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
Congratulations! You've successfully configured WBS Code Masks in your Aspose.Tasks project.
## Conclusion
In this tutorial, we've explored the step-by-step process of configuring WBS Code Masks using Aspose.Tasks for .NET. This powerful library provides developers with a seamless way to enhance project management capabilities within their .NET applications.

## FAQ's
### Can I use Aspose.Tasks for free?
Aspose.Tasks offers a free trial, which you can download [here](https://releases.aspose.com/).
### Where can I find additional support?
Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community support.
### How can I obtain a temporary license?
You can get a temporary license [here](https://purchase.aspose.com/temporary-license/).
### Is there detailed documentation available?
Yes, the comprehensive documentation is available [here](https://reference.aspose.com/tasks/net/).
### Where can I purchase Aspose.Tasks?
Purchase Aspose.Tasks [here](https://purchase.aspose.com/buy).

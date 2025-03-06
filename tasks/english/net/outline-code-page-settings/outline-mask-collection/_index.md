---
title: Master MS Project Outline Masks with Aspose.Tasks
linktitle: Collection of Outline Masks in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manipulate MS Project collection outline masks using Aspose.Tasks for .NET. Enhance productivity with this comprehensive tutorial.
weight: 15
url: /net/outline-code-page-settings/outline-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master MS Project Outline Masks with Aspose.Tasks

## Introduction
Are you looking to harness the power of Microsoft Project's outline masks using Aspose.Tasks for .NET? You've come to the right place! In this comprehensive tutorial, we'll guide you through the process step by step, ensuring you gain a solid understanding of how to effectively manipulate outline masks in your projects. Whether you're a seasoned developer or just getting started, this guide will equip you with the knowledge and skills needed to optimize your workflow.
## Prerequisites
Before diving into this tutorial, make sure you have the following prerequisites in place:
### 1. Installation of Aspose.Tasks for .NET
Ensure that you have Aspose.Tasks for .NET installed in your development environment. You can download the library from the Aspose website [here](https://releases.aspose.com/tasks/net/).
### 2. Basic Knowledge of C# and .NET Framework
Familiarize yourself with C# programming language and the .NET Framework, as this tutorial will utilize both.
### 3. Microsoft Project File
Have a Microsoft Project file (MPP) ready for testing purposes. You can use an existing file or create a new one for experimentation.
## Import Namespaces
Let's start by importing the necessary namespaces into your C# project. This step ensures that you have access to the required classes and functionalities provided by Aspose.Tasks for .NET.

Add the following namespaces at the beginning of your code file:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Now, let's break down the provided example into multiple steps and explain each step in detail:
## Step 1: Initialize the Project Object
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
Here, we create a new instance of the `Project` class and load an existing Microsoft Project file named "OutlineValues2010.mpp".
## Step 2: Access Outline Codes
```csharp
var outline = project.OutlineCodes[0];
```
We access the outline codes from the project. Outline codes are custom fields in Microsoft Project that allow you to categorize and organize tasks.
## Step 3: Clear Outline Masks
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
This step ensures that any existing outline masks are cleared before proceeding further.
## Step 4: Create Outline Masks
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
We create new outline masks and specify their types. In this example, we create a valid outline mask and a wrong one.
## Step 5: Insert and Edit Masks
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
Here, we insert a wrong mask into the collection and edit the length of a mask using its index.
## Step 6: Remove Masks
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
We remove the wrong mask from the collection based on its index.
## Step 7: Iterate Over Masks
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
This loop iterates over each outline mask in the collection and prints out its properties such as length, level, separator, and type.
## Step 8: Copy Masks to Another Project
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
Finally, we copy the outline masks from one project to another, ensuring consistency across different projects.
## Conclusion
Congratulations! You've successfully learned how to manipulate MS Project collection outline masks using Aspose.Tasks for .NET. By following this tutorial, you're now equipped with the skills to efficiently manage outline masks in your projects, ultimately enhancing your productivity and workflow.
## FAQ's
### Q1: Can I use Aspose.Tasks for .NET with different versions of Microsoft Project files?
A: Yes, Aspose.Tasks for .NET supports various versions of Microsoft Project files, including MPP, MPT, and XML formats.
### Q2: Is Aspose.Tasks for .NET compatible with .NET Core?
A: Yes, Aspose.Tasks for .NET is compatible with .NET Core, allowing you to use it in cross-platform applications.
### Q3: Can I customize the properties of outline masks according to my project requirements?
A: Absolutely! You can customize outline masks by adjusting their length, level, separator, and type to suit your specific project needs.
### Q4: Does Aspose.Tasks for .NET provide documentation and support?
A: Yes, Aspose.Tasks for .NET offers comprehensive documentation and dedicated support through their website and [forums](https://forum.aspose.com/c/tasks/15).
### Q5: Is there a free trial available for Aspose.Tasks for .NET?
A: Yes, you can access a free trial of Aspose.Tasks for .NET from their [website](https://releases.aspose.com/tasks/net/). to explore its features and functionalities before making a purchase.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Mastering MS Project Outline Values with Aspose.Tasks
linktitle: Managing Outline Values in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage MS Project outline values efficiently using Aspose.Tasks for .NET. Customize project outlines with ease.
type: docs
weight: 16
url: /net/outline-code-page-settings/outline-values/
---
## Introduction
In this tutorial, we'll explore how to manage Microsoft Project outline values using the Aspose.Tasks library for .NET. With Aspose.Tasks, you can easily manipulate outline codes, create new outline values, and customize project outlines according to your requirements.
## Prerequisites
Before you begin, ensure you have the following:
1. Installation of Aspose.Tasks for .NET: Download and install the Aspose.Tasks for .NET library from [here](https://releases.aspose.com/tasks/net/).
2. Development Environment: Make sure you have a development environment set up, such as Visual Studio, with .NET framework compatibility.
3. Basic Understanding of C# Programming: Familiarize yourself with C# programming language basics, as we'll be using C# to work with the Aspose.Tasks library.

## Import Namespaces
Start by importing the necessary namespaces into your C# code:
```csharp
    using System;
    using NUnit.Framework;
```
## Step 1: Load the Project File
```csharp
// The path to the documents directory.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
This step initializes a new Project object and loads the Microsoft Project file from the specified directory.
## Step 2: Define Outline Code Definitions
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
Here, we define two OutlineCodeDefinition objects and add them to the project's OutlineCodes collection.
## Step 3: Define Outline Mask
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
This step sets up an OutlineMask for the outline code definition.
## Step 4: Create Outline Values
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
In this step, we create two OutlineValue objects and set their properties such as value, value ID, type, description, and collapse status.

## Conclusion
Managing MS Project outline values using Aspose.Tasks for .NET is straightforward with the provided functionalities. By following the steps outlined in this tutorial, you can efficiently manipulate outline codes and values to customize project outlines according to your needs.
## FAQ's
### Q: Can I use Aspose.Tasks with other .NET frameworks?
A: Yes, Aspose.Tasks is compatible with various .NET frameworks, ensuring flexibility in your development environment.
### Q: Is there a trial version available for Aspose.Tasks?
A: Yes, you can access a free trial version of Aspose.Tasks from [here](https://releases.aspose.com/).
### Q: How can I get support for Aspose.Tasks?
A: For support and assistance, you can visit the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
### Q: Can I purchase a temporary license for Aspose.Tasks?
A: Yes, you can purchase a temporary license for Aspose.Tasks from [here](https://purchase.aspose.com/temporary-license/).
### Q: Where can I find detailed documentation for Aspose.Tasks?
A: You can refer to the comprehensive documentation available [here](https://reference.aspose.com/tasks/net/).

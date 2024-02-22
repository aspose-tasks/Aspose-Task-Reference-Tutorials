---
title: Save MS Project Files as Templates with Aspose.Tasks
linktitle: Save Template Options for Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to save Microsoft Project files as templates using Aspose.Tasks for .NET. Customize template settings for streamlined project management.
type: docs
weight: 18
url: /net/saving-options/save-template-options/
---
## Introduction
In this tutorial, we will walk through the process of saving a template using Aspose.Tasks for .NET. Templates are useful for standardizing project structures and settings for future use. We'll demonstrate how to save a project as a template, tuning its properties along the way.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Aspose.Tasks for .NET Library: Make sure you have the Aspose.Tasks for .NET library installed. You can download it from [here](https://releases.aspose.com/tasks/net/).
2. Knowledge of C# Programming: Basic knowledge of C# programming is required to understand and implement the provided code snippets.
3. Microsoft Project File: Have a Microsoft Project file (MPP format) ready that you want to save as a template.

## Import Namespaces
```csharp
using System;
using NUnit.Framework;
using Saving;
```
## Step 1: Load Project
First, we need to load the Microsoft Project file (.mpp) that we want to save as a template.
```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Step 2: Get Project File Info
Retrieve information about the loaded project file, such as its format.
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## Step 3: Configure Save Template Options
Create template save options and configure its properties according to your requirements. These options allow you to customize what data should be removed from the template.
```csharp
var options = new SaveTemplateOptions
{
	// Remove all fixed costs from the project template
	RemoveFixedCosts = true,
	// Remove all actual values from the project template
	RemoveActualValues = true,
	// Remove resource rates from the project template
	RemoveResourceRates = true,
	// Remove all baseline values from the project template
	RemoveBaselineValues = true
};
```
## Step 4: Save Project as Template
Save the project as a template with the specified options.
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## Step 5: Get Template File Info
Retrieve information about the saved template file, such as its format.
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
Congratulations! You have successfully saved a template using Aspose.Tasks for .NET, customizing its properties as needed.

## Conclusion
In this tutorial, we explored how to save a Microsoft Project file as a template using Aspose.Tasks for .NET. Templates are valuable for standardizing project structures and settings, streamlining future project creations.
## FAQ's
### Q: Can I customize which data to remove from the template?
A: Yes, you can configure the Save Template Options to remove specific data such as fixed costs, actual values, resource rates, and baseline values.
### Q: Is Aspose.Tasks for .NET compatible with all versions of Microsoft Project?
A: Aspose.Tasks for .NET provides extensive compatibility with various versions of Microsoft Project, ensuring seamless integration and functionality.
### Q: Can I apply templates to existing projects?
A: Yes, you can apply templates to existing projects by loading the template file and merging it with your current project as needed.
### Q: Does Aspose.Tasks for .NET support cross-platform development?
A: Aspose.Tasks for .NET is primarily designed for .NET framework applications running on Windows platforms.
### Q: Is technical support available for Aspose.Tasks for .NET?
A: Yes, you can seek technical assistance and guidance from the Aspose.Tasks community [forums](https://forum.aspose.com/c/tasks/15) or contact their support team directly.
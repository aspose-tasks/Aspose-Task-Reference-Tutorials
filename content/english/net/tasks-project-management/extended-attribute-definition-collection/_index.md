---
title: Master Extended Attribute Definitions MS Project in Aspose.Tasks
linktitle: Collection of Extended Attribute Definitions in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage extended attribute definitions in Microsoft Project using Aspose.Tasks for .NET. Customize and enhance your project data effortlessly.
type: docs
weight: 14
url: /net/tasks-project-management/extended-attribute-definition-collection/
---
## Introduction
In this tutorial, we will explore how to work with extended attribute definitions in Microsoft Project using Aspose.Tasks for .NET. Extended attributes offer a flexible way to customize and enhance project data, allowing users to add additional fields beyond the standard ones provided by default. With Aspose.Tasks, you can effortlessly manage these extended attributes to tailor your project management needs.
## Prerequisites
Before proceeding, ensure you have the following prerequisites installed:
- [.NET Framework](https://dotnet.microsoft.com/download)
- Aspose.Tasks for .NET library. You can download it from [here](https://releases.aspose.com/tasks/net/).

## Import Namespaces
First, you need to import the necessary namespaces to access Aspose.Tasks classes and methods in your .NET project. Follow these steps:
## Step 1: Open your .NET project
Open your .NET project in your preferred IDE, such as Visual Studio.
## Step 2: Add Aspose.Tasks namespace
Add the following line at the beginning of your code file to import the Aspose.Tasks namespace:
```csharp
using System;
using System.Collections.Generic;
using NUnit.Framework;
```

Now, let's break down the provided code examples into multiple steps for a comprehensive understanding:
## Step 1: Load the project file
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Step 2: Clear existing extended attribute definitions (optional)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Step 3: Create and add extended attribute definition for a task
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Step 4: Iterate over task extended attributes
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Step 5: Create and add extended attribute definition for a resource
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Step 6: Insert a resource extended attribute definition
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Step 7: Remove an extended attribute by index
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Conclusion
In this tutorial, we've covered the basics of working with extended attribute definitions in Microsoft Project using Aspose.Tasks for .NET. By following these steps, you can efficiently manage and customize extended attributes to suit your project management requirements.
## FAQ's
### Q: Can I modify existing extended attribute definitions?
A: Yes, you can modify existing extended attribute definitions or create new ones according to your needs.
### Q: Are extended attributes supported in all versions of Microsoft Project?
A: Yes, extended attributes are supported in most versions of Microsoft Project, including recent ones.
### Q: Can I use extended attributes to calculate custom fields?
A: Absolutely, extended attributes can be used to calculate custom fields based on specific criteria you define.
### Q: Is Aspose.Tasks compatible with other .NET frameworks?
A: Aspose.Tasks is compatible with various .NET frameworks, ensuring flexibility and ease of integration.
### Q: Where can I find more resources and support for Aspose.Tasks?
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for support and explore the documentation [here](https://reference.aspose.com/tasks/net/).

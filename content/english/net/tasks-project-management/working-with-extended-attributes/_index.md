---
title: Manipulate MS Project Extended Attributes with Aspose.Tasks
linktitle: Working with Extended Attributes in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to work with MS Project extended attributes using Aspose.Tasks for .NET. Manipulate task data programmatically with ease.
type: docs
weight: 11
url: /net/tasks-project-management/working-with-extended-attributes/
---
## Introduction
Aspose.Tasks for .NET is a powerful library that allows developers to manipulate Microsoft Project files programmatically. One of the key features of this library is its ability to work with MS Project extended attributes. Extended attributes provide additional customization and metadata to tasks in a project, enabling users to store and manage specific information beyond the standard task properties.
In this tutorial, we will explore how to work with MS Project extended attributes using Aspose.Tasks for .NET. We'll cover the prerequisites, import namespaces, and break down each example into multiple steps in a step-by-step guide format. By the end of this tutorial, you'll have a solid understanding of how to leverage extended attributes in your .NET applications.
## Prerequisites
Before we begin, make sure you have the following prerequisites:
### 1. Visual Studio Installed
Ensure you have Visual Studio installed on your system. You can download it from the website if you haven't already.
### 2. Aspose.Tasks for .NET Library
Download and install the Aspose.Tasks for .NET library from the [website](https://releases.aspose.com/tasks/net/).

## Import Namespaces
To start working with Aspose.Tasks for .NET, you need to import the necessary namespaces into your project. Follow these steps:
### Step 1: Open Visual Studio
Launch Visual Studio on your system.
### Step 2: Create a New Project
Create a new project or open an existing one where you want to use Aspose.Tasks.
### Step 3: Import Namespaces
Add the following namespaces at the beginning of your C# file:
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

Now that we have set up our environment let's dive into working with MS Project extended attributes using Aspose.Tasks for .NET.
## Step 1: Define Data Directory
Define the path to the directory where your MS Project file is located:
```csharp
String DataDir = "Your Document Directory";
```
Replace `"Your Document Directory"` with the actual path to your document directory.
## Step 2: Load the Project File
Load the MS Project file using the `Project` class:
```csharp
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
This code initializes a new instance of the `Project` class, loading the specified MS Project file.
## Step 3: Read Extended Attributes for Tasks
Iterate through tasks and their extended attributes to read information:
```csharp
foreach (var task in project.RootTask.Children)
{
    foreach (var attribute in task.ExtendedAttributes)
    {
        // Read common info about extended attribute
        Console.WriteLine("Extended Attribute: " + attribute.ToString());
    }
}
```
This code snippet loops through each task and its extended attributes, printing their information to the console.

## Conclusion
In this tutorial, we've learned how to work with MS Project extended attributes using Aspose.Tasks for .NET. By following the steps outlined above, you can efficiently manage and manipulate extended attribute data in your .NET applications.
## FAQ's
### Is Aspose.Tasks for .NET compatible with all versions of Microsoft Project?
Yes, Aspose.Tasks for .NET supports various versions of Microsoft Project, including 2003, 2007, 2010, 2013, 2016, and 2019.
### Can I use Aspose.Tasks for .NET to create new MS Project files?
Absolutely! Aspose.Tasks for .NET allows you to create, modify, and manipulate MS Project files programmatically.
### Does Aspose.Tasks for .NET require a license for commercial use?
Yes, you need to purchase a license for commercial use of Aspose.Tasks for .NET. However, you can also avail of a free trial to evaluate its capabilities.
### Can I customize extended attributes according to my project's requirements?
Yes, Aspose.Tasks for .NET provides extensive capabilities to customize extended attributes to suit your project's specific needs.
### Where can I get support if I encounter any issues while using Aspose.Tasks for .NET?
You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

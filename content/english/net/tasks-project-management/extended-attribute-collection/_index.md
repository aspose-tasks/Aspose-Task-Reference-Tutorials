---
title: Manage MS Project Attributes Collection in Aspose.Tasks
linktitle: Managing Extended Attribute Collection in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to efficiently manage MS Project extended attributes using Aspose.Tasks for .NET. Seamlessly manipulate task attributes with step-by-step guidance.
type: docs
weight: 12
url: /net/tasks-project-management/extended-attribute-collection/
---
## Introduction
Are you looking to efficiently manage MS Project extended attributes using Aspose.Tasks for .NET? In this tutorial, we'll guide you through the process step by step. Let's dive in!
## Prerequisites
Before we get started, ensure you have the following:
1. Visual Studio: Install Visual Studio on your system.
2. Aspose.Tasks for .NET: Download and install Aspose.Tasks for .NET from [here](https://releases.aspose.com/tasks/net/).
3. Basic Knowledge of C#: Familiarize yourself with C# programming language basics.

## Import Namespaces
Begin by importing the necessary namespaces into your project:
```csharp
    using System;
    using NUnit.Framework;
```
## Step 1: Load Project File
First, load the MS Project file using the following code snippet:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Step 2: Access Task and Extended Attributes
Access a specific task and its extended attributes:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Step 3: Clear Extended Attributes
Clear existing extended attributes if needed:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Step 4: Create Extended Attribute Definitions
Create definitions for new extended attributes:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Step 5: Iterate Over Task Extended Attributes
Iterate over task extended attributes:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Step 6: Add Extended Attributes
Add new extended attributes to the task:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Step 7: Work with Extended Attributes
Perform operations on extended attributes as required.
## Step 8: Remove Extended Attributes
Remove extended attributes by index or conditionally:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Step 9: Copy Attributes to Another Task
Copy attributes to another task within the same or different project:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Conclusion
Managing MS Project extended attribute collections becomes seamless with Aspose.Tasks for .NET. By following the steps outlined in this tutorial, you can efficiently handle extended attributes, enhancing your project management capabilities.
## FAQ's
### Q: Can I manipulate extended attributes across multiple projects?
A: Yes, you can copy extended attributes between tasks in different projects using Aspose.Tasks for .NET.
### Q: Are there limitations on the number of extended attributes per task?
A: Aspose.Tasks for .NET imposes no inherent limitations on the number of extended attributes per task.
### Q: Can I create custom extended attribute fields?
A: Absolutely! Aspose.Tasks for .NET allows you to define custom extended attribute fields tailored to your project requirements.
### Q: Does Aspose.Tasks for .NET support reading and writing to MS Project files of various versions?
A: Yes, Aspose.Tasks for .NET supports MS Project file formats across different versions.
### Q: Is there a trial version available for Aspose.Tasks for .NET?
A: Yes, you can download a free trial from [here](https://releases.aspose.com/).

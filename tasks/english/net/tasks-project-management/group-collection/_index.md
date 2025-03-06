---
title: Managing Project Collections in Aspose.Tasks
linktitle: Managing Group Collection in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage MS Project collections efficiently using Aspose.Tasks for .NET. Follow our step-by-step guide.
weight: 26
url: /net/tasks-project-management/group-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Managing Project Collections in Aspose.Tasks

## Introduction
In this tutorial, we'll explore how to manage group MS Project collections using Aspose.Tasks for .NET. Managing group collections is crucial for organizing and manipulating tasks and resources efficiently within your project.
## Prerequisites
Before proceeding with this tutorial, make sure you have the following prerequisites:
1. Aspose.Tasks for .NET Library: Download and install the Aspose.Tasks for .NET library from the [download link](https://releases.aspose.com/tasks/net/).
2. Basic Knowledge of C#: Familiarize yourself with C# programming language basics as this tutorial involves coding in C#.
3. Development Environment: Set up a development environment such as Visual Studio or any other IDE that supports .NET development.

## Import Namespaces
First, let's import the necessary namespaces to work with Aspose.Tasks functionalities in our C# code.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Step 1: Load the Project
```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
This step involves loading the MS Project file into the Aspose.Tasks project object, allowing us to perform operations on it.
## Step 2: Iterate Over Task Groups
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Here, we iterate over task groups within the project, printing details such as index, name, and visibility in the menu for each group.
## Step 3: Iterate Over Resource Groups
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Similarly, this step iterates over resource groups, displaying their index, name, and visibility in the menu.
## Step 4: Clear and Copy Groups to Another Project
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Clear other project's groups
otherProject.TaskGroups.Clear();
// Copy groups to other project
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Here, we clear the groups of another project and then copy groups from the original project to it.
## Step 5: Add a Custom Task Group
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
In this step, we create a custom task group and add it to the other project if it's not already present.
## Step 6: Remove All Groups
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Finally, we remove all groups from the other project.

## Conclusion
Managing group MS Project collections in Aspose.Tasks for .NET is essential for organizing and manipulating project data efficiently. By following the steps outlined in this tutorial, you can effectively handle task and resource groups within your projects, improving overall project management.
## FAQ's
### Is Aspose.Tasks for .NET compatible with all versions of MS Project?
Aspose.Tasks for .NET supports various versions of Microsoft Project, including 2003, 2007, 2010, 2013, 2016, and 2019.
### Can I customize group properties using Aspose.Tasks for .NET?
Yes, you can customize group properties such as name and visibility using Aspose.Tasks for .NET.
### Does Aspose.Tasks for .NET offer cross-platform compatibility?
Aspose.Tasks for .NET primarily targets the .NET framework, but it can be used in cross-platform scenarios with .NET Core and .NET Standard.
### How can I get support for Aspose.Tasks for .NET?
You can get support for Aspose.Tasks for .NET through the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
### Is there a trial version available for Aspose.Tasks for .NET?
Yes, you can download a free trial version of Aspose.Tasks for .NET from the [website](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

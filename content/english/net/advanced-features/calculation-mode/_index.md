---
title: Calculation Mode in Aspose.Tasks
linktitle: Calculation Mode in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage calculation modes effectively in Aspose.Tasks for .NET to streamline project scheduling and task dependencies.
type: docs
weight: 29
url: /net/advanced-features/calculation-mode/
---
## Introduction

Aspose.Tasks for .NET is a powerful API that allows developers to work with Microsoft Project files programmatically in their .NET applications. One crucial aspect of working with project files is managing calculation modes, which dictate how tasks and project schedules are calculated and updated. In this tutorial, we'll delve into the various calculation modes supported by Aspose.Tasks for .NET and demonstrate how to use them effectively.

## Prerequisites

Before you begin, ensure you have the following:

1. Visual Studio: Make sure you have Visual Studio installed on your system.
2. Aspose.Tasks for .NET: Download and install the Aspose.Tasks for .NET library from [here](https://releases.aspose.com/tasks/net/).
3. Basic understanding of C# programming: Familiarize yourself with C# programming concepts.

## Import Namespaces

Before we start working with Aspose.Tasks for .NET, let's import the necessary namespaces:

```csharp
using System;
using NUnit.Framework;

```

## Applying Automatic Calculation Mode

### Step 1: Create a new Project instance

Initialize a new `Project` object and set its `CalculationMode` property to `CalculationMode.Automatic`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

### Step 2: Set project start date and add tasks

Define the start date of the project and add tasks to it.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Step 3: Link tasks

Establish dependencies between tasks.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Step 4: Verify recalculated dates

Check if the dates have been recalculated automatically.

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

## Applying Manual Calculation Mode

### Step 1: Create a new Project instance

Initialize a new `Project` object and set its `CalculationMode` property to `CalculationMode.Manual`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

### Step 2: Set project start date and add tasks

Define the start date of the project and add tasks to it.

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

### Step 3: Verify task properties

Check if task properties are set correctly in manual mode.

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

### Step 4: Link tasks and verify dates

Link tasks together and check if their dates are not recalculated.

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

## Applying None Calculation Mode

### Step 1: Create a new Project instance

Initialize a new `Project` object and set its `CalculationMode` property to `CalculationMode.None`.

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

### Step 2: Add a new task

Add a new task to the project.

```csharp
var task = project.RootTask.Children.Add("Task");
```

### Step 3: Verify task properties

Check if task properties are not automatically calculated.

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Conclusion

In this tutorial, we've explored the calculation modes available in Aspose.Tasks for .NET and learned how to apply them in practical scenarios. Whether you need automatic, manual, or no calculation mode, Aspose.Tasks provides the flexibility to suit your project's requirements.

## FAQ's

### Q1: Can I change the calculation mode dynamically during runtime?

A1: Yes, you can change the calculation mode of a project at any point during runtime by modifying the `CalculationMode` property.

### Q2: Does Aspose.Tasks support other project management file formats besides Microsoft Project?

A2: Aspose.Tasks primarily focuses on Microsoft Project file formats, but it also supports other formats like Primavera P6 XML, Primavera DB, and Asta Powerproject XML.

### Q3: Is Aspose.Tasks suitable for both small-scale and enterprise-level projects?

A3: Absolutely! Aspose.Tasks is designed to cater to the needs of both small-scale and enterprise-level projects with its comprehensive features and robust APIs.

### Q4: Can I integrate Aspose.Tasks with other .NET libraries and frameworks?

A4: Yes, you can seamlessly integrate Aspose.Tasks with other .NET libraries and frameworks to enhance the functionality of your applications.

### Q5: Is there a community forum or support channel available for Aspose.Tasks users?

A5: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community support and discussions.

---
title: Using Tree Algorithm in Aspose.Tasks
linktitle: Using Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to effectively manipulate task hierarchies in your .NET projects using Aspose.Tasks' Tree Algorithm.
type: docs
weight: 13
url: /net/advanced-concepts/tree-algorithm/
---
## Introduction

Aspose.Tasks for .NET provides powerful functionalities for working with project management tasks, resources, and schedules. One such feature is the Tree Algorithm, which allows users to manipulate task hierarchies efficiently. In this tutorial, we'll explore how to utilize the Tree Algorithm in Aspose.Tasks for .NET to gather common work and update work values within a project.

## Prerequisites

Before we begin, ensure that you have the following prerequisites in place:

1. Visual Studio: Make sure you have Visual Studio installed on your system.
2. Aspose.Tasks for .NET: Download and install Aspose.Tasks for .NET from [here](https://releases.aspose.com/tasks/net/).
3. Basic understanding of C#: Familiarity with C# programming language is required to follow along with the examples.

## Import Namespaces

In your C# project, import the necessary namespaces to work with Aspose.Tasks functionalities:

```csharp
using System;

using Aspose.Tasks.Util;

```

Now, let's break down each example into multiple steps:

## Step 1: Load Project File

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Load the project file into memory using the `Project` class.

## Step 2: Define Task Hierarchy

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Define the task hierarchy by adding parent and child tasks.

## Step 3: Set Task Properties

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Set properties such as start date, duration, and finish date for tasks.

## Step 4: Add Resource

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Add resources to the project and assign them to tasks as needed.

## Step 5: Apply Tree Algorithm

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Initialize the `WorkAccumulator` class and apply the Tree Algorithm to gather common work.

## Step 6: Update Task Work

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Update the work values for tasks based on the gathered information.

## Conclusion

In this tutorial, we've learned how to utilize the Tree Algorithm in Aspose.Tasks for .NET to manipulate task hierarchies effectively. By following the step-by-step guide, you can efficiently manage tasks and resources within your projects.

## FAQ's

### Q1: What is Aspose.Tasks for .NET?

A1: Aspose.Tasks for .NET is a powerful API that allows developers to manipulate Microsoft Project files programmatically using C#.

### Q2: Can I download a free trial of Aspose.Tasks for .NET?

A2: Yes, you can download a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).

### Q3: Where can I find documentation for Aspose.Tasks for .NET?

A3: You can find the documentation for Aspose.Tasks for .NET [here](https://reference.aspose.com/tasks/net/).

### Q4: How can I get support for Aspose.Tasks for .NET?

A4: For support related to Aspose.Tasks for .NET, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Is there a temporary license available for testing purposes?

A5: Yes, you can obtain a temporary license for testing purposes from [here](https://purchase.aspose.com/temporary-license/).

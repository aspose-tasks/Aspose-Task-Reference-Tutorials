---
title: Add Resource to Project with Tree Algorithm in Aspose.Tasks
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to add resource to project and calculate task duration using Aspose.Tasks' Tree Algorithm, and assign resources to tasks in .NET.
weight: 13
url: /net/advanced-concepts/tree-algorithm/
date: 2026-03-19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Resource to Project with Tree Algorithm in Aspose.Tasks

## Introduction

In this tutorial you’ll discover **how to add resource to project** by leveraging the powerful Tree Algorithm supplied by Aspose.Tasks for .NET. We’ll walk through creating a task hierarchy, calculating task duration, and assigning resources to tasks—all in a clear, step‑by‑step manner that you can copy into your own solution.

## Quick Answers
- **What does the Tree Algorithm do?** It traverses a task hierarchy to aggregate work values efficiently.  
- **Which primary operation does this guide cover?** Adding a resource to a project and updating work totals.  
- **Do I need a license?** A temporary or full license is required for production use.  
- **Can I use this with .NET Core?** Yes, Aspose.Tasks supports .NET Framework and .NET Core.  
- **How long does implementation take?** Around 10‑15 minutes for a basic project file.

## What is “add resource to project” in Aspose.Tasks?

Adding a resource to a project means creating a `Resource` object, defining its type (e.g., work), and linking it to one or more tasks via `ResourceAssignments`. This enables the scheduler to calculate effort, cost, and overall project duration.

## Why use the Tree Algorithm for resource work calculations?

The Tree Algorithm walks the task tree once, accumulating work from leaf tasks up to their summary tasks. This approach is far more efficient than iterating over each task individually, especially in large projects with deep hierarchies. It also guarantees that summary work values stay in sync with their children.

## Prerequisites

Before we dive in, make sure you have the following:

1. **Visual Studio** – any recent edition (2019, 2022, or later).  
2. **Aspose.Tasks for .NET** – download it from [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – you should be comfortable with classes, objects, and simple LINQ.

## Import Namespaces

In your C# project, import the necessary namespaces to work with Aspose.Tasks functionalities:

```csharp
using Aspose.Tasks;
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

## Step 3: Set Task Properties (including **calculate task duration**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Here we **calculate task duration** by converting work hours into a `Duration` object and then derive the finish date.

## Step 4: Add Resource (**assign resources to tasks**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

This snippet **adds a resource to the project** and **assigns resources to tasks** so the scheduler knows who is responsible for the work.

## Step 5: Apply Tree Algorithm

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Initialize the `WorkAccumulator` class and apply the Tree Algorithm to gather common work across the hierarchy.

## Step 6: Update Task Work

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Update the work values for tasks based on the gathered information.

## Common Issues & Tips

- **Missing calendar settings:** If the finish date looks off, ensure the project calendar is correctly configured before calling `GetFinishDateByStartAndWork`.  
- **Resource type mismatch:** Always set `Rsc.Type` to `ResourceType.Work` for effort‑based resources; otherwise, the work accumulation may return zero.  
- **Pro tip:** After updating work, call `project.Save("UpdatedProject.mpp")` to persist changes.

## Conclusion

By following these steps you now know how to **add resource to project**, **calculate task duration**, and **assign resources to tasks** using Aspose.Tasks' Tree Algorithm. This method streamlines hierarchy management and keeps summary work values accurate with minimal code.

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

## Frequently Asked Questions

**Q: Can I use this approach with an existing large project file?**  
A: Absolutely. The Tree Algorithm works on any `Project` instance, regardless of size.

**Q: Does the algorithm also update cost values?**  
A: The example focuses on work, but you can extend it to cost by accumulating `Tsk.Cost` in a similar fashion.

**Q: What .NET versions are supported?**  
A: Aspose.Tasks supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, and .NET 6+.

**Q: How do I handle multiple resources per task?**  
A: Add each resource with `project.ResourceAssignments.Add(task, resource)`; the accumulator will sum their work automatically.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
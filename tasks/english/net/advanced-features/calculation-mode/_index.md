---
title: How to Set Calculation Mode in Aspose.Tasks for .NET
linktitle: How to Set Calculation Mode in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
description: Learn how to set calculation mode in Aspose.Tasks for .NET, covering automatic, manual calculation mode, and none mode to manage task dependencies.
weight: 29
url: /net/advanced-features/calculation-mode/
date: 2026-03-24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set Calculation Mode in Aspose.Tasks for .NET

## Introduction

Aspose.Tasks for .NET is a powerful API that lets you work with Microsoft Project files programmatically. One of the most important settings you’ll encounter is the **calculation mode**, which controls how task dates and project schedules are updated. In this tutorial you’ll learn **how to set calculation** mode, explore **automatic calculation mode**, **manual calculation mode**, and **none calculation mode**, and see how these options affect **manage task dependencies**, **create project start date**, and **link tasks finish‑start** relationships.

## Quick Answers
- **What is calculation mode?** It determines whether task dates are recomputed automatically, manually, or not at all.  
- **Why use manual calculation mode?** To gain full control over when the schedule is refreshed, useful in bulk updates.  
- **Which mode is default?** Automatic calculation mode, which updates dates instantly after changes.  
- **Can I change the mode at runtime?** Yes—simply set the `CalculationMode` property on the `Project` object.  
- **Do I need a license?** A valid Aspose.Tasks license is required for production use.

## What is “how to set calculation” in Aspose.Tasks?
Setting the calculation mode is as simple as assigning an enum value to the `Project.CalculationMode` property. The enum provides three options: `Automatic`, `Manual`, and `None`. Choosing the right mode depends on your workflow—whether you want instant updates, batch processing, or complete control.

## Prerequisites

Before you begin, make sure you have:

1. **Visual Studio** – any recent version (2019, 2022, or later).  
2. **Aspose.Tasks for .NET** – download and install the library from [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – you should be comfortable with creating console applications and using NuGet packages.

## Import Namespaces

Before we start working with Aspose.Tasks for .NET, let's import the necessary namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## How to Set Calculation Mode

Below you’ll find step‑by‑step examples for each calculation mode. The code blocks are unchanged from the original tutorial; the surrounding explanations have been expanded for clarity.

### Applying Automatic Calculation Mode

Automatic mode recalculates dates instantly whenever you modify tasks or links.

#### Step 1: Create a new Project instance

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Automatic
};
```

#### Step 2: Set project start date and add tasks

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Step 3: Link tasks (finish‑to‑start)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

#### Step 4: Verify recalculated dates

```csharp
Console.WriteLine("Task1 Start + 1 Equals Task2 Start : {0} ", task1.Get(Tsk.Start).AddDays(1).Equals(task2.Get(Tsk.Start)));
// Add more verifications as needed
```

### Applying Manual Calculation Mode

Manual mode disables automatic updates, giving you the chance to batch‑process changes before forcing a recalculation.

#### Step 1: Create a new Project instance

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.Manual
};
```

#### Step 2: Set project start date and add tasks

```csharp
project.Set(Prj.StartDate, new DateTime(2015, 4, 15));
var task1 = project.RootTask.Children.Add("Task 1");
var task2 = project.RootTask.Children.Add("Task 2");
```

#### Step 3: Verify task properties

```csharp
Console.WriteLine("Task1.Id Equals 1 : {0} ", task1.Get(Tsk.Id).Equals(1));
// Add more verifications as needed
```

#### Step 4: Link tasks and verify dates (no automatic recalculation)

```csharp
project.TaskLinks.Add(task1, task2, TaskLinkType.FinishToStart);
```

### Applying None Calculation Mode

None mode turns off all internal calculations. Use it when you only need to read or export data without any schedule changes.

#### Step 1: Create a new Project instance

```csharp
var project = new Project
{
   CalculationMode = CalculationMode.None
};
```

#### Step 2: Add a new task

```csharp
var task = project.RootTask.Children.Add("Task");
```

#### Step 3: Verify task properties (no automatic IDs)

```csharp
Console.WriteLine("Task.Id Equals 0 : {0} ", task.Get(Tsk.Id).Equals(0));
// Add more verifications as needed
```

## Common Issues and Solutions

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| Dates don’t update after linking tasks | Project is in **Manual** or **None** mode | Set `project.CalculationMode = CalculationMode.Automatic` or call `project.Calculate()` manually |
| Task IDs stay at 0 | Using **None** mode prevents ID generation | Switch to **Automatic** or **Manual** mode, then recalculate |
| Linking fails with `ArgumentException` | The start date of the predecessor is later than the successor when using **Manual** mode without recalculation | Ensure correct start dates or recalculate after adding links |

## Frequently Asked Questions

**Q1: Can I change the calculation mode dynamically during runtime?**  
A1: Yes, you can modify the `CalculationMode` property at any point in your code and then call `project.Calculate()` if you need an immediate update.

**Q2: Does Aspose.Tasks support other project management file formats besides Microsoft Project?**  
A2: Aspose.Tasks primarily focuses on Microsoft Project formats, but it also supports Primavera P6 XML, Primavera DB, and Asta Powerproject XML.

**Q3: Is Aspose.Tasks suitable for both small‑scale and enterprise‑level projects?**  
A3: Absolutely. The API scales from simple task lists to complex, multi‑phase enterprise schedules.

**Q4: Can I integrate Aspose.Tasks with other .NET libraries and frameworks?**  
A4: Yes, you can combine Aspose.Tasks with ASP.NET, WPF, Xamarin, or any other .NET technology to build rich project‑management solutions.

**Q5: Is there a community forum or support channel available for Aspose.Tasks users?**  
A5: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community support and discussions.

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
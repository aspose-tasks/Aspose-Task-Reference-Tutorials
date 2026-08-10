---
title: Add Resource to Project and Set Availability in Aspose.Tasks
linktitle: Working with Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to add resource to project and set resource availability periods using Aspose.Tasks for .NET. Step‑by‑step guide for managing resource calendars.
weight: 17
url: /net/advanced-features/working-with-availability-periods/
date: 2026-04-06
keywords:
- add resource to project
- set resource availability
- configure work schedule
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Resource to Project and Set Availability in Aspose.Tasks

## Introduction

In this tutorial you'll learn **how to add resource to project** and then define its availability periods using the Aspose.Tasks .NET library. Managing resource calendars is essential for realistic project schedules, and the steps below walk you through the whole process—from creating a project instance to printing out each period’s details.

## Quick Answers
- **What is the main goal?** To add a resource to a project and configure its availability periods.  
- **Which library is required?** Aspose.Tasks for .NET.  
- **Do I need a license for production?** Yes, a commercial license is required.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Implementation time?** Typically under 15 minutes for basic scenarios.

## What is “add resource to project”?

Adding a resource to a project creates a placeholder for a person, equipment, or material that can be assigned to tasks. Once the resource exists, you can **set resource availability**, define its work calendar, and let the scheduler respect those constraints.

## Why configure work schedule and availability periods?

- **Accurate planning:** Tasks are scheduled only when the resource is actually free.  
- **Cost control:** Availability units reflect part‑time effort, helping you calculate labor costs correctly.  
- **Resource leveling:** The engine can automatically level over‑allocations when it knows each resource’s calendar.

## Prerequisites

1. Visual Studio (or any .NET‑compatible IDE).  
2. Aspose.Tasks for .NET – download from [here](https://releases.aspose.com/tasks/net/).  
3. Basic C# knowledge.

## Import Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## How to add resource to project?

### Step 1: Create a new `Project` instance

```csharp
var project = new Project();
```

This object represents the whole project file in memory.

### Step 2: Add a resource to the project

```csharp
var resource = project.Resources.Add("Work Resource");
```

The call creates a **resource** named *Work Resource* that you can later attach to tasks.

### Step 3: Define availability periods

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` is a helper method (implementation not shown) that returns a collection of `AvailabilityPeriod` objects. Each period specifies a start date, an end date, and the units (percentage of full‑time effort) the resource is available.

### Step 4: Add the periods to the resource

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Here we **set resource availability** by looping through the collection and adding each period to the resource’s calendar.

### Step 5: Display the availability details

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

The console output lets you verify that the periods were stored correctly.

## Common Pitfalls & Tips

- **Date precision:** `AvailableFrom` and `AvailableTo` are `DateTime` values; ensure they are set to midnight if you want whole‑day periods.  
- **Units range:** Valid values are 0‑100 %; values outside this range will throw an exception.  
- **Over‑lapping periods:** Overlapping periods are merged automatically, but it’s clearer to keep them distinct.

## Frequently Asked Questions

### Q1: Can I use Aspose.Tasks for .NET in commercial projects?
A1: Yes, Aspose.Tasks for .NET can be used in commercial projects. You can purchase a license [here](https://purchase.aspose.com/buy).

### Q2: Is there a free trial available for Aspose.Tasks for .NET?
A2: Yes, you can obtain a free trial of Aspose.Tasks for .NET [here](https://releases.aspose.com/).

### Q3: Where can I find documentation for Aspose.Tasks for .NET?
A3: You can find the documentation [here](https://reference.aspose.com/tasks/net/).

### Q4: How can I get support for Aspose.Tasks for .NET?
A4: You can get support from the community forum [here](https://forum.aspose.com/c/tasks/15).

### Q5: Do you offer temporary licenses for Aspose.Tasks for .NET?
A5: Yes, temporary licenses are available [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.Tasks for .NET (latest stable release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
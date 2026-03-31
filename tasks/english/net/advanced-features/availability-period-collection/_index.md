---
title: Project Resource Availability – Managing Availability Periods in Aspose.Tasks
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage availability periods for resources and achieve effective project resource availability with Aspose.Tasks for .NET. This step‑by‑step guide shows how to add, update, and remove availability periods.
weight: 18
url: /net/advanced-features/availability-period-collection/
date: 2026-03-21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Project Resource Availability: Collection of Availability Periods in Aspose.Tasks

Managing **project resource availability** is a core part of successful project planning. In this tutorial you’ll learn **how to manage availability** for resources using the Aspose.Tasks for .NET API, step by step, from loading a project to copying periods between resources.

## Quick Answers
- **What is the main class for availability periods?** `AvailabilityPeriod` in the `Aspose.Tasks` namespace.  
- **Can I clear existing periods?** Yes, call `resource.AvailabilityPeriods.Clear()`.  
- **How do I add a new period?** Create an `AvailabilityPeriod` object and use `Add` or `Insert`.  
- **Is it possible to copy periods to another resource?** Absolutely – use `CopyTo` and then add each item to the target resource.  
- **Do I need a license for production use?** Yes, a commercial Aspose.Tasks license is required for non‑trial deployments.

## What is project resource availability?
Project resource availability defines the dates and units (percentage of capacity) when a resource can be assigned to tasks. By controlling these periods you prevent overallocation and improve schedule accuracy.

## Why use Aspose.Tasks to manage availability periods?
- **Full .NET integration** – no COM interop, pure managed code.  
- **Fine‑grained control** – set exact start/end dates and fractional units.  
- **Easy copying** – move availability data between resources without manual parsing.  
- **Performance‑optimized** – works with large MPP files efficiently.

## Prerequisites
1. **Visual Studio** – any recent version (2019, 2022, or later).  
2. **Aspose.Tasks for .NET** – download from [here](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – you should be comfortable with classes, collections, and LINQ.

## Import Namespaces

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

We import the core Aspose.Tasks namespace together with standard .NET collections that we’ll need later.

## Step 1: Initialize the Project and Resource

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Here we load an existing MPP file and fetch the resource whose availability we want to edit (ID = 1).

## Step 2: Clear Existing Availability Periods

```csharp
resource.AvailabilityPeriods.Clear();
```

Clearing removes any previously defined periods, giving us a clean slate.

## Step 3: Add Availability Periods

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

We retrieve a collection of `AvailabilityPeriod` objects (the `GetPeriods` helper is assumed to be defined elsewhere) and add each one, checking that the collection is writable.

## Step 4: Insert a New Availability Period

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

This creates a custom period for the year 2013 and inserts it at position 1 (second slot) if it isn’t already present.

## Step 5: Display Availability Periods

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

A quick console dump shows the total count and each period’s details – handy for debugging or verification.

## Step 6: Copy Availability Periods to Another Resource

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

We copy the whole collection into an array, clear the target resource’s periods, and then repopulate it. This demonstrates how to duplicate availability data across resources.

## Step 7: Update and Remove Availability Periods

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Here we adjust the `AvailableUnits` for the penultimate period and then remove the 2013 period we added earlier.

## Common Issues and Solutions
- **Read‑only collection error** – Ensure the project is not opened in a read‑only mode or that you have called `resource.AvailabilityPeriods.Clear()` before adding new items.  
- **Overlapping periods** – Aspose.Tasks does not automatically merge overlaps; you may need to write custom logic to detect and resolve them.  
- **Incorrect date format** – Always use `DateTime` objects; string parsing can lead to locale‑specific bugs.

## Frequently Asked Questions

**Q: Can I add custom fields to availability periods?**  
A: No, availability periods in Aspose.Tasks for .NET do not support custom fields.

**Q: Are availability periods linked to specific tasks?**  
A: No, they are associated with resources and define when the resource is generally available for tasks.

**Q: Can I import availability periods from external sources?**  
A: Yes, you can import periods from CSV, XML, or a database by creating `AvailabilityPeriod` objects and adding them to the collection.

**Q: How do I handle overlapping availability periods?**  
A: Overlaps are not resolved automatically; you need to implement custom validation to merge or reject conflicting periods.

**Q: Is there a limit to the number of availability periods a resource can have?**  
A: There is no hard‑coded limit, but very large collections may affect performance; consider consolidating periods where possible.

## Conclusion

In this guide we covered everything you need to know to manage **project resource availability** with Aspose.Tasks for .NET—from initializing a project and clearing old data, to adding, inserting, copying, updating, and removing availability periods. Mastering these steps helps you keep resource calendars accurate and your project schedules realistic.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
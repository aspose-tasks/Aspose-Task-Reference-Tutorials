---
title: Collection of Availability Periods in Aspose.Tasks
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage availability periods for resources in Aspose.Tasks for .NET. This step-by-step tutorial guides you through adding, updating, and removing availability periods, ensuring effective project resource planning.
weight: 18
url: /net/advanced-features/availability-period-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Collection of Availability Periods in Aspose.Tasks

## Introduction

In this tutorial, we'll explore how to work with the availability period collection of a resource in Aspose.Tasks for .NET. Managing availability periods is crucial for project management, allowing us to define when resources are available for tasks within a project.

## Prerequisites

Before we begin, make sure you have the following:

1. Visual Studio: Ensure you have Visual Studio installed on your system.
2. Aspose.Tasks for .NET: Download and install the Aspose.Tasks for .NET library from [here](https://releases.aspose.com/tasks/net/).
3. Basic Understanding: Familiarity with C# and .NET framework.

## Import Namespaces

First, we need to import the necessary namespaces to our project:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Let's break down the example code into multiple steps and understand each part:

## Step 1: Initialize the Project and Resource

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Here, we're loading a project file and obtaining a specific resource by its ID.

## Step 2: Clear Existing Availability Periods

```csharp
resource.AvailabilityPeriods.Clear();
```

We clear any existing availability periods associated with the resource.

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

We iterate through a collection of availability periods and add them to the resource.

## Step 4: Insert a New Availability Period

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

We create a new availability period for the year 2013 and insert it into the collection.

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

We print out the count and details of each availability period associated with the resource.

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

We copy the availability periods from one resource to another.

## Step 7: Update and Remove Availability Periods

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

We update the available units for a period and remove specific periods from the collection.

## Conclusion

In this tutorial, we've learned how to work with availability period collections in Aspose.Tasks for .NET. Managing resource availability is essential for effective project planning and execution.

## FAQ's

### Q1: Can I add custom fields to availability periods?

A1: No, availability periods in Aspose.Tasks for .NET do not support custom fields.

### Q2: Are availability periods linked to specific tasks?

A2: No, availability periods are associated with resources and define when they are available for tasks in general.

### Q3: Can I import availability periods from external sources?

A3: Yes, you can import availability periods from various data sources using Aspose.Tasks for .NET APIs.

### Q4: How do I handle overlapping availability periods?

A4: Aspose.Tasks for .NET does not provide built-in mechanisms to handle overlapping periods. You may need to implement custom logic to manage such scenarios.

### Q5: Is there a limit to the number of availability periods a resource can have?

A5: There is no predefined limit to the number of availability periods a resource can have, but performance may degrade with a large number of periods.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Managing Day Type Collection in Aspose.Tasks
linktitle: Managing Day Type Collection in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage day type collections efficiently in Aspose.Tasks for .NET. Create, modify, and manipulate calendar exceptions with ease.
type: docs
weight: 28
url: /net/calendar-scheduling/day-type-collection/
---
## Introduction

Aspose.Tasks for .NET provides robust functionality for managing day type collections, crucial for defining weekly calendar exceptions in project management applications. In this tutorial, we'll explore how to utilize the `DayTypeCollection` class efficiently. 

## Prerequisites

Before we proceed with the tutorial, make sure you have the following prerequisites:

1. Visual Studio: Ensure you have Visual Studio installed on your system.
2. Aspose.Tasks for .NET: Download and install the Aspose.Tasks for .NET library from [here](https://releases.aspose.com/tasks/net/).
3. Basic Knowledge of C#: Familiarity with C# programming language and .NET framework concepts.

## Import Namespaces

To get started, you need to import the necessary namespaces into your C# project:

```csharp
using Aspose.Tasks;
using System;


```

Now, let's break down the provided example into multiple steps:

## Step 1: Load Project and Access Calendar

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

This step initializes a new project instance and retrieves the calendar by its UID.

## Step 2: Iterate Through Calendar Exceptions

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Here, we iterate through each calendar exception and print its name and associated day types.

## Step 3: Modify Calendar Exceptions

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

This step demonstrates how to modify calendar exceptions by adding, removing, or updating day types.

## Step 4: Create and Manipulate New Calendar Exceptions

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

In this final step, we create new calendar exceptions and manipulate them by adding and copying day types.

## Conclusion

In conclusion, managing day type collections in Aspose.Tasks for .NET is essential for defining and modifying weekly calendar exceptions in project management applications. By following the step-by-step guide provided in this tutorial, you can effectively utilize the `DayTypeCollection` class to handle various calendar operations.

## FAQ's

### Q1: Can Aspose.Tasks for .NET be used to create Gantt charts programmatically?

A1: Yes, Aspose.Tasks for .NET provides APIs to create and manipulate Gantt charts in .NET applications.

### Q2: Is Aspose.Tasks for .NET compatible with both .NET Core and .NET Framework?

A2: Yes, Aspose.Tasks for .NET supports both .NET Core and .NET Framework.

### Q3: How can I get support for Aspose.Tasks for .NET?

A3: You can get support by visiting the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) where you can ask questions and interact with other users.

### Q4: Does Aspose.Tasks for .NET offer a free trial?

A4: Yes, you can get a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).

### Q5: Can I purchase a temporary license for Aspose.Tasks for .NET?

A5: Yes, temporary licenses are available for purchase from the [Aspose website](https://purchase.aspose.com/temporary-license/).

---
title: Collection of Calendar Exceptions in Aspose.Tasks
linktitle: Collection of Calendar Exceptions in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to efficiently handle calendar exceptions in your .NET projects using Aspose.Tasks, ensuring accurate scheduling and resource management.
type: docs
weight: 13
url: /net/calendar-scheduling/calendar-exception-collection/
---
## Introduction

In project management, precise scheduling is vital for success. However, real-world scenarios often require deviations from standard schedules due to holidays, special events, or other factors. Aspose.Tasks for .NET provides a robust solution for managing such exceptions through its Calendar Exception Collection feature. This tutorial will guide you through the process of utilizing this functionality step by step.

## Prerequisites

Before diving into the tutorial, ensure you have the following prerequisites:

1. Aspose.Tasks for .NET: Make sure you have the library installed. You can download it [here](https://releases.aspose.com/tasks/net/).
2. Basic knowledge of C#: Familiarity with C# programming language will be helpful in understanding the examples.
3. Development Environment: Set up your preferred development environment, such as Visual Studio or JetBrains Rider.

## Import Namespaces

Before you begin working with Aspose.Tasks for .NET, you need to import the required namespaces into your project. This step enables you to access the classes and methods necessary for managing calendar exceptions.

```csharp
using System;
using System.Collections.Generic;
using NUnit.Framework;

```

Now, let's break down the example provided into multiple steps:

## Step 1: Load Project and Retrieve Calendar

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

In this step, we load a project file and retrieve the desired calendar by its UID.

## Step 2: Clear Existing Exceptions and Set Standard Calendar

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

This step clears any existing exceptions from the calendar and sets it to a standard configuration.

## Step 3: Define and Add Working Time Exception

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

This step defines a working time exception with specific start and end dates, along with working times within those dates, and adds it to the calendar.

## Step 4: Define and Add Non-Working Time Exceptions

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

This step defines non-working time exceptions, such as holidays, and adds them to the calendar.

## Step 5: Display Calendar Exceptions

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

This step displays the added calendar exceptions along with their details.

## Step 6: Remove All Exceptions

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Finally, this step removes all exceptions from the calendar.

## Conclusion

Managing calendar exceptions is crucial for accurate project scheduling. Aspose.Tasks for .NET simplifies this task by providing a comprehensive set of features, including the Calendar Exception Collection. By following the steps outlined in this tutorial, you can efficiently handle various scheduling scenarios within your projects.

## FAQ's

### Q1: Can I add multiple exceptions to a single calendar?

A1: Yes, you can add multiple exceptions to a calendar using the `AddRange` method.

### Q2: How do I handle recurring exceptions, such as weekly holidays?

A2: You can programmatically calculate recurring exceptions and add them to the calendar using custom logic.

### Q3: Is it possible to import calendar exceptions from external sources?

A3: Yes, you can read calendar exceptions from external sources like databases or CSV files and integrate them into your project.

### Q4: What happens if there are overlapping exceptions in the calendar?

A4: Aspose.Tasks for .NET allows you to handle overlapping exceptions by defining priorities or resolving conflicts based on your project requirements.

### Q5: Can I customize the working times for each day within an exception?

A5: Yes, you can specify custom working times for individual days within an exception to accommodate specific scheduling needs.

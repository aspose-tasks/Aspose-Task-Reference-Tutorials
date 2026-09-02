---
title: Delete Calendar Exception with Aspose.Tasks
linktitle: Delete Calendar Exception with Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to delete calendar exception in Aspose.Tasks for .NET and check exception date while managing ASP.NET calendar scheduling.
date: 2026-04-13
weight: 12
url: /net/calendar-scheduling/calendar-exceptions/
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Delete Calendar Exception with Aspose.Tasks

## Introduction

In this tutorial, you'll learn how to **delete calendar exception** and manage other calendar exceptions in Aspose.Tasks using the .NET framework. Calendar exceptions let you model holidays, temporary closures, or any special periods where the normal working schedule changes. Understanding how to add, query, and remove these exceptions is essential for accurate project scheduling, especially when working with **ASP.NET calendar scheduling** scenarios.

## Quick Answers
- **What is the primary method to remove an exception?** Use the `Delete()` method on the `CalendarException` object.  
- **Which class checks a date against an exception?** `CalendarException.CheckException()`—useful to **check exception date**.  
- **Do I need a license to run the code?** Yes, a valid Aspose.Tasks license is required for production use.  
- **Can I add multiple exceptions to one calendar?** Absolutely; the `Exceptions` collection supports many entries.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a Calendar Exception?

A **calendar exception** represents a deviation from the regular working calendar—think of it as a rule that says “on these dates, work hours are different or none at all.” In Aspose.Tasks, each exception can have its own working times, recurrence pattern, and flags that indicate whether the day is working.

## Why Manage Calendar Exceptions in ASP.NET Calendar Scheduling?

- **Accurate timelines:** Projects automatically respect holidays and special closures, preventing unrealistic deadlines.  
- **Flexibility:** You can define daily, weekly, monthly, or yearly patterns, matching real‑world business calendars.  
- **Automation:** Programmatically checking an exception date lets you build dynamic scheduling logic in ASP.NET applications.

## Prerequisites

- Basic knowledge of C# programming.  
- Visual Studio (any recent version).  
- Aspose.Tasks for .NET library added to your project (via NuGet or manual reference).  

## Import Namespaces

First, import the namespaces you’ll need:

```csharp
using Aspose.Tasks;
using System;
```

## Step 1: Delete Calendar Exception

Removing an unwanted exception is straightforward. The following code loads a project, selects the first calendar, displays basic info, deletes the first exception, and then shows the updated count.

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **Pro tip:** Always verify the exception index exists before calling `Delete()` to avoid `IndexOutOfRangeException`.

## Step 2: Get Working Time of a Calendar Exception

If you need to inspect the working hours defined for an exception, use `GetWorkingTime()`. This example also demonstrates how to **check exception date** with `CheckException`.

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Step 3: Define Calendar Exceptions

Below is a complete walk‑through that shows how to **add**, **check**, and **remove** calendar exceptions. Notice the use of `CheckException` to **check exception date** for a specific moment.

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Common Issues & Tips

| Issue | Reason | Solution |
|-------|--------|----------|
| **`IndexOutOfRangeException` when deleting** | Trying to delete an exception that doesn’t exist. | Verify `calendar.Exceptions.Count` > index before calling `Delete()`. |
| **Incorrect working times** | Not setting `DayWorking` or `WorkingTimes` properly. | Use `exception.WorkingTimes.Add(new WorkingTime(...))` to define explicit periods. |
| **Exception not recognized** | `CheckException` returns `false` because the date falls outside the defined range. | Double‑check `FromDate`/`ToDate` and the `Type` (Daily, Weekly, etc.). |

## Frequently Asked Questions

**Q: Can I add multiple exceptions to a single calendar?**  
A: Yes, you can add as many exceptions as needed to represent holidays, maintenance windows, or any special scheduling rules.

**Q: How do I **check exception date** for a specific day?**  
A: Use the `CheckException(DateTime date)` method on a `CalendarException` instance. It returns `true` if the supplied date falls within the exception range.

**Q: Is it possible to remove an existing exception from a calendar?**  
A: Absolutely. Access the `Exceptions` collection and call `Remove()` or invoke `Delete()` on the specific `CalendarException` object.

**Q: What types of calendar exceptions are supported?**  
A: Aspose.Tasks supports Daily, Weekly, Monthly, and Yearly exception types, giving you flexibility to model almost any recurrence pattern.

**Q: Can I customize working hours for specific exception dates?**  
A: Yes. After creating an exception, populate its `WorkingTimes` collection with `WorkingTime` objects that define start and finish times for that day.

## Conclusion

We've walked through the complete lifecycle of **delete calendar exception** operations, from inspecting existing exceptions to adding new ones and checking dates. Mastering these techniques ensures your project schedules respect real‑world calendars, making your ASP.NET calendar scheduling implementations robust and reliable.

---

**Last Updated:** 2026-04-13  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
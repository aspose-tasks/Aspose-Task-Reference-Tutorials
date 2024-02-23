---
title: Handling Calendar Exceptions in Aspose.Tasks
linktitle: Handling Calendar Exceptions in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage calendar exceptions in Aspose.Tasks for .NET with step-by-step tutorials and examples.
type: docs
weight: 12
url: /net/calendar-scheduling/calendar-exceptions/
---
## Introduction

In this tutorial, we'll explore how to manage calendar exceptions in Aspose.Tasks using the .NET framework. Calendar exceptions allow us to define special dates or periods in a project calendar where the regular working schedule is altered, such as holidays or temporary closures. We'll cover various methods to handle calendar exceptions step by step, using Aspose.Tasks for .NET.

## Prerequisites

Before we begin, ensure you have the following prerequisites:
- Basic knowledge of C# programming language.
- Visual Studio installed on your system.
- Aspose.Tasks for .NET library added to your project.

## Import Namespaces

Firstly, let's import the necessary namespaces for our project:

```csharp
using System;


```

## Step 1: Deleting a Calendar Exception

To delete a calendar exception, follow these steps:

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

## Step 2: Getting Working Time of a Calendar Exception

To retrieve the working time of a calendar exception, follow these steps:

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

## Step 3: Defining Calendar Exceptions

To add or remove calendar exceptions, follow these steps:

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

    // Check if a date is an exception
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

## Conclusion

In this article, we've covered various aspects of handling calendar exceptions in Aspose.Tasks for .NET. By following the provided steps, you can effectively manage exceptions in your project schedules, ensuring accurate representation of working hours and special events.

## FAQ's

### Q1: Can I add multiple exceptions to a single calendar?

A1: Yes, you can add multiple exceptions to a calendar to accommodate various special dates or periods.

### Q2: How can I check if a specific date is an exception?

A2: You can use the `CheckException()` method to verify if a particular date falls under an exception.

### Q3: Is it possible to remove an existing exception from a calendar?

A3: Yes, you can remove exceptions by accessing the `Exceptions` collection of the calendar and using the `Remove()` method.

### Q4: What types of calendar exceptions are supported?

A4: Aspose.Tasks supports various types of exceptions, including daily, weekly, monthly, and yearly exceptions, providing flexibility in defining exception rules.

### Q5: Can I customize working hours for specific exception dates?

A5: Yes, you can define custom working times for individual exception dates using the appropriate methods provided by Aspose.Tasks.

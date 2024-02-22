---
title: Mastering Working Times in Aspose.Tasks
linktitle: Collection of Working Times in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Explore the power of Aspose.Tasks for .NET in managing project timelines efficiently. Customize calendars, set working times, and streamline your projects with ease.
type: docs
weight: 14
url: /net/time-recurrence-configuration/working-time-collection/
---
## Introduction
Are you looking to master the art of managing working times in Aspose.Tasks for .NET? Look no further! In this step-by-step guide, we'll delve into the intricacies of working time collection using Aspose.Tasks, empowering you to efficiently handle custom calendars and streamline your project timelines.
## Prerequisites
Before we embark on this journey, ensure you have the following prerequisites in place:
- Aspose.Tasks for .NET Library: Download and install the Aspose.Tasks for .NET library from the [official Aspose.Tasks release page](https://releases.aspose.com/tasks/net/).
- Working Environment: Set up a suitable development environment, preferably using a .NET-compatible IDE.
## Import Namespaces
In your project, import the necessary namespaces to access the Aspose.Tasks functionalities:
```csharp
    using System;
    using System.Collections.Generic;
    using NUnit.Framework;
```
Now, let's break down the tutorial into multiple steps, ensuring a smooth learning experience.
## Step 1: Create a Custom Calendar
Begin by creating a new project and adding a custom calendar to it:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Step 2: Define Working Days
Set up default working days from Monday to Friday:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Step 3: Configure Saturday Working Times
Specify working times for Saturdays:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Step 4: Print Saturday Working Periods
Print the configured working times for Saturday:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Step 5: Configure Sunday Working Times
Define working times for Sundays:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Step 6: Print Sunday Working Periods
Print the configured working times for Sunday:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Step 7: Add Custom Days to Calendar
Include the configured Saturday and Sunday in the calendar:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Step 8: Traverse Through Working Times
Traverse through the working times and display them for each day in the calendar:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Now that you've successfully navigated through the steps, you're equipped to harness the power of Aspose.Tasks for .NET in managing working times effectively.
## Conclusion
Mastering the collection of working times in Aspose.Tasks empowers you to customize project calendars, ensuring precise scheduling and efficient resource utilization. Dive into your projects with confidence, armed with the knowledge gained from this comprehensive guide.
## Frequently Asked Questions
### Is Aspose.Tasks suitable for large-scale project management?
Yes, Aspose.Tasks is designed to handle projects of varying sizes, providing robust features for efficient project management.
### Can I integrate Aspose.Tasks with other .NET libraries?
Certainly! Aspose.Tasks seamlessly integrates with other .NET libraries, enhancing its versatility and compatibility.
### How often is Aspose.Tasks updated?
Aspose.Tasks is regularly updated to incorporate new features, enhancements, and compatibility improvements. Check the [official release page](https://releases.aspose.com/tasks/net/) for the latest updates.
### Is there a free trial available for Aspose.Tasks?
Yes, you can explore Aspose.Tasks with a free trial by visiting [this link](https://releases.aspose.com/).
### Where can I seek support for Aspose.Tasks?
For any queries or assistance, visit the [Aspose.Tasks support forum](https://forum.aspose.com/c/tasks/15).

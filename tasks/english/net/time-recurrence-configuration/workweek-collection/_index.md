---
title: Customize Work Weeks in Aspose.Tasks
linktitle: Collection of Workweeks in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to customize work weeks in Aspose.Tasks for .NET. Step-by-step guide for creating personalized project calendars. Download now!
weight: 17
url: /net/time-recurrence-configuration/workweek-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Customize Work Weeks in Aspose.Tasks

## Introduction
Welcome to our tutorial on creating a custom work week using Aspose.Tasks for .NET! In this step-by-step guide, we'll walk you through the process of defining a personalized work week for a calendar in your project. Aspose.Tasks is a powerful library that empowers developers to efficiently work with Microsoft Project documents in their .NET applications.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
1. Visual Studio: Make sure you have Visual Studio installed on your machine.
2. Aspose.Tasks for .NET: Download and install the Aspose.Tasks library. You can find the download link [here](https://releases.aspose.com/tasks/net/).
3. Basic knowledge of C#: Familiarize yourself with C# programming language basics.
## Import Namespaces
In your C# project, make sure to import the necessary namespaces:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Step 1: Create a Project and Calendar
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Step 2: Define a Custom Work Week
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Step 3: Set Working Days
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Step 4: Display Work Weeks Information
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
This comprehensive guide empowers you to efficiently create and manage custom work weeks using Aspose.Tasks for .NET.
## Conclusion
In conclusion, Aspose.Tasks for .NET provides a robust solution for handling project calendars with custom work weeks. By following this tutorial, you've learned how to create and display information about custom work weeks in your project.
## FAQs
### Can I have multiple custom work weeks in a single project?
Yes, you can add multiple custom work weeks to a project calendar.
### How can I modify existing work weeks?
Use the provided `WorkWeek` properties and methods to modify existing work weeks.
### Is Aspose.Tasks compatible with .NET Core?
Yes, Aspose.Tasks supports .NET Core.
### Can I export the project with custom work weeks to Microsoft Project file format?
Absolutely, Aspose.Tasks allows you to save your project in various formats, including Microsoft Project.
### Where can I seek support for Aspose.Tasks-related queries?
Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any support or assistance.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

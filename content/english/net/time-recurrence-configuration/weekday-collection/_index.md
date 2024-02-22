---
title: Mastering Weekdays in Aspose.Tasks
linktitle: Collection of Weekdays in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Discover the power of Aspose.Tasks for .NET in managing weekdays effortlessly. Customize working days, remove weekends, and create specialized calendars with ease.
type: docs
weight: 11
url: /net/time-recurrence-configuration/weekday-collection/
---
## Introduction
Aspose.Tasks for .NET is a powerful library that facilitates efficient manipulation of project management data. In this tutorial, we will explore the collection of weekdays in Aspose.Tasks, enabling you to customize working days, remove weekends, and create specialized calendars to meet your project requirements. Whether you are a seasoned developer or a newcomer, this step-by-step guide will walk you through the process of working with weekdays in Aspose.Tasks for .NET.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
- Install the Aspose.Tasks for .NET library. You can download it from the official [Aspose.Tasks for .NET download page](https://releases.aspose.com/tasks/net/).
- Familiarity with C# programming language.
- Integrated development environment (IDE) such as Visual Studio.
## Import Namespaces
Begin by importing the necessary namespaces into your C# project:
```csharp
    using System;
    using System.Collections.Generic;
    using NUnit.Framework;
```
## Step 1: Create a Project Instance
Initialize a new Aspose.Tasks project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Step 2: Access the Calendar
Retrieve the project calendar:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Step 3: Customize Weekdays
Clear existing weekdays and set default working days:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Add other weekdays similarly...
```
## Step 4: Add Working Times
Add working times for specific weekdays:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Step 5: Display Calendar Information
Output calendar details to the console:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Display each weekday and working times...
```
## Step 6: Remove Weekends
Remove Saturday and Sunday from the weekdays:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Step 7: Display Updated Working Times
Output updated working times after removing weekends:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Display each updated weekday and working times...
```
## Step 8: Create a 24-Hour Calendar
Create a 24-hour calendar and copy weekdays:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Conclusion
In this tutorial, we explored the powerful capabilities of Aspose.Tasks for .NET in managing weekdays within project calendars. From customizing working days to creating specialized 24-hour calendars, Aspose.Tasks simplifies the process, offering flexibility and control in project management.
## Frequently Asked Questions
### Q: Can I use Aspose.Tasks for .NET with other programming languages?
A: Aspose.Tasks primarily supports .NET languages, but it also offers versions for Java.
### Q: Is there a free trial available for Aspose.Tasks for .NET?
A: Yes, you can download a free trial from the official [Aspose.Tasks releases page](https://releases.aspose.com/).
### Q: How can I get support for Aspose.Tasks for .NET?
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community support or consider purchasing a support plan.
### Q: Where can I find comprehensive documentation for Aspose.Tasks for .NET?
A: Refer to the official [Aspose.Tasks for .NET documentation](https://reference.aspose.com/tasks/net/) for detailed information.
### Q: How do I obtain a temporary license for Aspose.Tasks for .NET?
A: You can acquire a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).

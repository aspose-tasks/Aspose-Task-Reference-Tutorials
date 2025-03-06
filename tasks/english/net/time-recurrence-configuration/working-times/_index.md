---
title: Configuring Working Times in Aspose.Tasks
linktitle: Configuring Working Times in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Enhance project scheduling in .NET with Aspose.Tasks. Configure working times effortlessly for precise resource management. Download the library now!
type: docs
weight: 13
url: /net/time-recurrence-configuration/working-times/
---
## Introduction
In project management, precise control over working times is crucial for accurate scheduling and resource allocation. Aspose.Tasks for .NET provides a powerful solution for handling working time information within your projects. This tutorial will guide you through the process of configuring working times using Aspose.Tasks in a .NET environment.
## Prerequisites
Before diving into the tutorial, ensure you have the following:
- Basic understanding of C# programming language.
- Aspose.Tasks for .NET library installed. You can download it [here](https://releases.aspose.com/tasks/net/).
- Visual Studio or any preferred C# development environment set up.
## Import Namespaces
Start by importing the necessary namespaces to access the Aspose.Tasks functionalities:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## Step 1: Create Calendar
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
Here, we initiate a new project and create a calendar named "MyCalendar" based on the standard calendar. This calendar will be used to define specific working times.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## Step 2: Display Work Week Information
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
This step prints the total number of working days in the specified calendar.
## Step 3: Working Times Details
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
In this part, we iterate through each day of the week, printing the day type and associated working times. You can customize working times for each weekday according to your project requirements.
## Conclusion
Effectively configuring working times in Aspose.Tasks for .NET ensures accurate project planning and resource management. By following this step-by-step guide, you can seamlessly integrate working time adjustments into your project workflows.
## Frequently Asked Questions
### Is Aspose.Tasks suitable for large-scale project management?
Yes, Aspose.Tasks is designed to handle projects of various sizes, offering robust features for efficient project management.
### Can I set different working times for different team members?
Absolutely. You can customize working times on a per-resource basis, allowing for individualized schedules.
### Does Aspose.Tasks support integration with other project management tools?
Yes, Aspose.Tasks facilitates integration with various project management tools, enhancing interoperability.
### Is it possible to import/export project data in different formats?
Aspose.Tasks supports multiple file formats, enabling seamless import/export operations for project data.
### How frequently are Aspose.Tasks updates released?
Updates are regularly released to ensure compatibility with the latest technologies and address user feedback.

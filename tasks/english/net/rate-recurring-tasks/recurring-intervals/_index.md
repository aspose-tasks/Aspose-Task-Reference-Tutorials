---
title: Effortless MS Project Recurring Intervals in Aspose.Tasks
linktitle: Managing Recurring Intervals in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Discover how to effortlessly manage recurring intervals in MS Project using Aspose.Tasks for .NET. 
weight: 12
url: /net/rate-recurring-tasks/recurring-intervals/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Effortless MS Project Recurring Intervals in Aspose.Tasks

## Introduction
Are you looking to manage recurring intervals efficiently in Microsoft Project files using Aspose.Tasks for .NET? This comprehensive tutorial will guide you through the process step by step, ensuring you can effortlessly handle recurring intervals in your projects. Before diving into the tutorial, let's go over some prerequisites to ensure you're ready to get started.
## Prerequisites
Before proceeding with this tutorial, make sure you have the following:
1. Knowledge of C# Programming: Basic understanding of C# programming language and its syntax is required.
2. Visual Studio Installed: Ensure you have Visual Studio installed on your system for coding and compiling the .NET applications.
3. Aspose.Tasks for .NET Library: Download and install the Aspose.Tasks for .NET library. You can get it from [here](https://releases.aspose.com/tasks/net/).

## Import Namespaces
Begin by importing the necessary namespaces to access the functionalities provided by the Aspose.Tasks for .NET library.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Now, let's break down each example into multiple steps and explain them in detail.
## Step 1: Initialize Project Object:
```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
Here, we initialize a new instance of the `Project` class by providing the path to the Microsoft Project file.
## Step 2: Set Status Date:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
This step sets the status date of the project to its start date.
## Step 3: Access Gantt Chart View:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
We access the Gantt Chart view of the project.
## Step 4: Read Progress Line:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
This step retrieves the recurring interval for progress lines from the Gantt Chart view.
## Step 5: Display Interval Information:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Here, we display information about the interval, weekly week number, and weekly days.
## Step 6: Redefine Recurring Interval:
```csharp
var newInterval = new RecurringInterval();
```
We create a new instance of `RecurringInterval` to redefine the recurring interval.
## Step 7: Set Monthly Progress Lines:
```csharp
// Set monthly progress lines by day.
interval.MonthlyDay = true;
// Set the day number of monthly progress lines.
interval.MonthlyDayDayNumber = 1;
// Set the month number of monthly progress lines.
interval.MonthlyDayMonthNumber = 1;
// Set progress lines by first or last predefined day.
interval.MonthlyFirstLast = true;
// Set the first or the last day type of monthly progress lines.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Set the month number of progress lines.
interval.MonthlyFirstLastMonthNumber = 1;
```
These steps configure the monthly progress lines according to specified parameters.
## Step 8: Update Progress Lines:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
We update the progress lines in the Gantt Chart view with the newly defined recurring interval.
## Step 9: Save Project as PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Finally, we save the project with the updated recurring interval as a PDF file.

## Conclusion
In conclusion, managing recurring intervals in Microsoft Project files using Aspose.Tasks for .NET is made simple with the comprehensive functionalities provided by the library. By following the step-by-step guide outlined in this tutorial, you can efficiently handle recurring intervals in your projects, enhancing productivity and organization.
### FAQ's
### Can I use Aspose.Tasks for .NET with other programming languages?
Yes, Aspose.Tasks for .NET can be used with any .NET supported language such as C# and VB.NET.
### Is there a trial version available for Aspose.Tasks for .NET?
Yes, you can download a free trial version from [here](https://releases.aspose.com/).
### How can I get support for Aspose.Tasks for .NET?
You can get support from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
### Can I purchase a temporary license for Aspose.Tasks for .NET?
Yes, you can purchase a temporary license from [here](https://purchase.aspose.com/temporary-license/).
### Where can I find the complete documentation for Aspose.Tasks for .NET?
The complete documentation can be found [here](https://reference.aspose.com/tasks/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

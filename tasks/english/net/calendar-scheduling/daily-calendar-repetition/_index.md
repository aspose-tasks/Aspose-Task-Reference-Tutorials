---
title: Daily Calendar Repetition in Aspose.Tasks
linktitle: Daily Calendar Repetition in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to create recurring tasks with daily calendar repetitions in Aspose.Tasks for .NET. Enhance project management efficiency effortlessly.
weight: 25
url: /net/calendar-scheduling/daily-calendar-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Daily Calendar Repetition in Aspose.Tasks

## Introduction

Aspose.Tasks for .NET provides a powerful set of tools for managing tasks and projects programmatically. One of its notable features is the ability to handle daily calendar repetitions efficiently. In this tutorial, we'll explore how to utilize the `DailyCalendarRepetition` class along with other relevant classes to create recurring tasks with daily repetitions based on a specified calendar.

## Prerequisites

Before we begin, ensure you have the following set up:

1. Installation: Make sure you have Aspose.Tasks for .NET installed. If not, you can download it from [here](https://releases.aspose.com/tasks/net/).

2. Namespace Importing: Import the necessary namespaces into your project:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Step 1: Initialize the Project

Firstly, we need to load an existing project or create a new one to work with:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Step 2: Define the Calendar

Next, we create a calendar with a 24-hour duration and associate it with the project:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Step 3: Set Recurring Task Parameters

Now, let's set the parameters for our recurring task. We define its name, duration, recurrence pattern, and range:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## Step 4: Set Calendar for Task

Associate the defined calendar with the task:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Step 5: Add Task to Project

Add the task with defined parameters to the project:

```csharp
project.RootTask.Children.Add(parameters);
```

## Step 6: Save the Project

Finally, save the project with the added recurring task:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Now you've successfully created a project with a recurring task set to repeat daily based on a 24-hour calendar using Aspose.Tasks for .NET!

## Conclusion

In this tutorial, we've demonstrated how to utilize Aspose.Tasks for .NET to handle daily calendar repetitions efficiently. By following these steps, you can seamlessly integrate recurring tasks into your projects, enhancing productivity and organization.

## FAQ's

### Q1: Can I customize the duration of each repetition?

A1: Yes, you can adjust the duration of each repetition according to your requirements by modifying the parameters in the code.

### Q2: Is it possible to set different calendars for different tasks within the same project?

A2: Absolutely, Aspose.Tasks allows you to assign specific calendars to individual tasks, offering flexibility in scheduling.

### Q3: Does Aspose.Tasks support other recurrence patterns apart from daily?

A3: Yes, Aspose.Tasks provides a wide range of recurrence patterns such as weekly, monthly, yearly, etc., catering to diverse project needs.

### Q4: Can I visualize the recurring tasks created using Aspose.Tasks?

A4: Certainly, Aspose.Tasks offers visualization options to help you analyze and track recurring tasks effectively.

### Q5: Is there a trial version available for Aspose.Tasks?

A5: Yes, you can avail of a free trial of Aspose.Tasks from [here](https://releases.aspose.com/) to explore its features before making a purchase.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

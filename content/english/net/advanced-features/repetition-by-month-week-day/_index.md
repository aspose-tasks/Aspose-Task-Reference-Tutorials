---
title: Repetition by Month Week Day in Aspose.Tasks
linktitle: Repetition by Month Week Day in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to set up repetitions by month, week, and day in Aspose.Tasks for .NET to automate recurring tasks efficiently.
type: docs
weight: 26
url: /net/advanced-features/repetition-by-month-week-day/
---
## Introduction

In the realm of software development, particularly in project management applications, the ability to handle recurring tasks efficiently is paramount. Aspose.Tasks for .NET is a powerful library designed to streamline the creation and management of project tasks, including recurring ones. One such functionality provided by Aspose.Tasks is the ability to set up repetitions by month, week, and day, ensuring that tasks are executed on schedule without manual intervention.

## Prerequisites

Before diving into the intricacies of setting up repetitions by month, week, and day using Aspose.Tasks for .NET, make sure you have the following prerequisites in place:

1. Basic Understanding of C#: Familiarity with the C# programming language is essential to comprehend and implement the code examples provided.
   
2. Installation of Aspose.Tasks for .NET: Ensure that you have downloaded and installed the Aspose.Tasks for .NET library. You can obtain the library from the [download page](https://releases.aspose.com/tasks/net/).

3. Access to a .mpp Project File: Have a Microsoft Project file (.mpp) ready, as we'll be utilizing it to demonstrate the implementation of repetitions by month, week, and day.

## Import Namespaces

To get started with utilizing Aspose.Tasks for .NET in your C# application, you need to import the necessary namespaces. Here's how you can do it:

```csharp
using System;
using NUnit.Framework;
using Saving;

```

Let's break down the provided code snippet into multiple steps to understand each part thoroughly.

## Step 1: Load Project File

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

This step involves creating a new instance of the `Project` class and loading an existing Microsoft Project file (`Project1.mpp`) from the specified directory.

## Step 2: Define Recurring Task Parameters

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

In this step, we define the parameters for a recurring task. We specify the task name, duration, repetition pattern (monthly), and recurrence range (end by a specific date).

## Step 3: Add Recurring Task to Project

```csharp
project.RootTask.Children.Add(parameters);
```

Here, we add the defined recurring task parameters to the root task of the project.

## Step 4: Save Project File

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Finally, we save the modified project file with the added recurring task.

## Conclusion

In conclusion, setting up repetitions by month, week, and day in Aspose.Tasks for .NET is a straightforward process that empowers developers to automate the management of recurring tasks within their projects efficiently. By following the steps outlined in this tutorial, you can seamlessly integrate this functionality into your C# applications, saving time and effort in project management.

## FAQ's

###Q1: Can I customize the recurrence pattern beyond the provided examples?

A1: Yes, Aspose.Tasks for .NET offers extensive customization options for recurrence patterns, allowing you to tailor them to your specific requirements.

###Q2: Is there a trial version available for Aspose.Tasks for .NET?

A2: Yes, you can obtain a free trial of Aspose.Tasks for .NET from the [releases page](https://releases.aspose.com/).

###Q3: How can I obtain support for Aspose.Tasks for .NET?

A3: You can seek assistance and engage with the community on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

###Q4: Are temporary licenses available for Aspose.Tasks for .NET?

A4: Yes, you can acquire temporary licenses from the [purchase page](https://purchase.aspose.com/temporary-license/) for testing and evaluation purposes.

###Q5: Where can I find comprehensive documentation for Aspose.Tasks for .NET?

A5: You can refer to the detailed [documentation](https://reference.aspose.com/tasks/net/) available on the Aspose website for in-depth guidance on utilizing the library.

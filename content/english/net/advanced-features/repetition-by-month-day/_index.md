---
title: Repetition by Month Day in Aspose.Tasks
linktitle: Repetition by Month Day in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage recurring tasks in .NET projects with Aspose.Tasks. Step-by-step guide for handling repetition by month day.
type: docs
weight: 25
url: /net/advanced-features/repetition-by-month-day/
---
## Introduction

In the realm of .NET development, Aspose.Tasks stands as a powerful tool for managing project tasks and schedules. It offers a plethora of functionalities to streamline project management workflows, including handling recurring tasks. Repetition by month day is a common requirement in project scheduling, and Aspose.Tasks provides robust support for this scenario.

## Prerequisites

Before diving into the tutorial, ensure you have the following prerequisites:

1. Basic Understanding of C#: Familiarity with C# programming language is necessary to grasp the concepts discussed in this tutorial.
2. Installation of Aspose.Tasks for .NET: Make sure you have installed Aspose.Tasks for .NET. You can download it from [here](https://releases.aspose.com/tasks/net/).
3. Integrated Development Environment (IDE): Have an IDE like Visual Studio installed on your system for coding convenience.

## Import Namespaces

In your C# project, import the necessary namespaces to access Aspose.Tasks functionalities:

```csharp
using System;
using NUnit.Framework;
using Saving;

```

Let's break down the provided code example into step-by-step guide format:

## Step 1: Load Project File

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

This line of code initializes a new instance of the `Project` class, loading the project file named "Project1.mpp".

## Step 2: Define Recurring Task Parameters

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

This section defines the parameters for the recurring task, including its name, duration, repetition pattern, and recurrence range.

## Step 3: Add Task to Project

```csharp
project.RootTask.Children.Add(parameters);
```

Here, we add the recurring task parameters to the project.

## Step 4: Save Project File

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Finally, the modified project is saved with the added recurring task.

## Conclusion

In this tutorial, we've explored how to handle repetition by month day in Aspose.Tasks for .NET. By following the provided steps, you can efficiently manage recurring tasks within your project schedules.

## FAQ's

### Q1: Is Aspose.Tasks compatible with all versions of .NET?

A1: Aspose.Tasks supports various versions of the .NET framework, ensuring compatibility across different environments.

### Q2: Can I customize the recurrence pattern further?

A2: Yes, Aspose.Tasks offers extensive customization options for defining recurrence patterns according to specific project requirements.

### Q3: Does Aspose.Tasks provide support for other project management functionalities?

A3: Absolutely, Aspose.Tasks offers a wide range of features for project management, including task tracking, resource allocation, and Gantt chart generation.

### Q4: Is there a trial version available for Aspose.Tasks?

A4: Yes, you can avail of a free trial from [here](https://releases.aspose.com/) to explore Aspose.Tasks' capabilities before making a purchase decision.

### Q5: Where can I seek assistance if I encounter issues or have queries?

A5: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to seek support from the community or the Aspose team.

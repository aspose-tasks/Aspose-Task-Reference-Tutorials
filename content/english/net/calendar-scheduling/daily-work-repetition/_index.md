---
title: Daily Work Repetition in Aspose.Tasks
linktitle: Daily Work Repetition in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to create daily recurring tasks in Microsoft Project files using Aspose.Tasks for .NET. Boost productivity and organization effortlessly.
type: docs
weight: 26
url: /net/calendar-scheduling/daily-work-repetition/
---
## Introduction

Aspose.Tasks for .NET is a powerful library that enables developers to manipulate Microsoft Project files with ease. Among its myriad features is the ability to handle recurring tasks efficiently. In this tutorial, we'll delve into the Daily Work Repetition functionality, which allows for the creation of tasks that repeat daily within a project.

## Prerequisites

Before diving into this tutorial, make sure you have the following:

- Basic knowledge of C# and .NET framework.
- Visual Studio installed on your system.
- Aspose.Tasks for .NET library. You can download it [here](https://releases.aspose.com/tasks/net/).
- Familiarity with Microsoft Project files (.mpp).

## Import Namespaces

Before we begin, ensure you import the necessary namespaces:

```csharp
using System;
using System.Diagnostics.CodeAnalysis;


```

Let's break down the provided example into multiple steps:

## Step 1: Load the Project File

First, load the project file using the `Project` class:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Step 2: Define Recurring Task Parameters

Define the parameters for the recurring task:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## Step 3: Set Calendar and Task Start Date

Set the calendar and start date for the task:

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## Conclusion

In this tutorial, we explored how to utilize Aspose.Tasks for .NET to create recurring tasks with daily work repetition. By following these steps, you can efficiently manage tasks within your projects, ensuring smooth workflow and organization.

## FAQ's

### Q1: Can I customize the recurrence pattern further?

A1: Yes, you can adjust parameters such as start date, occurrence number, and repetition interval to tailor the recurrence pattern according to your requirements.

### Q2: Is Aspose.Tasks compatible with different versions of Microsoft Project?

A2: Yes, Aspose.Tasks supports various versions of Microsoft Project, ensuring compatibility and seamless integration.

### Q3: How can I handle exceptions or modifications to recurring tasks?

A3: Aspose.Tasks provides robust functionality to manage exceptions and modifications within recurring tasks, allowing for flexibility and customization.

### Q4: Can I export the project to different formats?

A4: Absolutely, Aspose.Tasks offers support for exporting projects to various formats including PDF, HTML, XML, and more, facilitating easy sharing and collaboration.

### Q5: Does Aspose.Tasks offer technical support?

A5: Yes, Aspose.Tasks provides comprehensive technical support through its forum, where you can seek assistance, share experiences, and engage with fellow users.

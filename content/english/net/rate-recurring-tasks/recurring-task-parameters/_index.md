---
title: Setting Recurring Task Parameters in Aspose.Tasks
linktitle: Setting Recurring Task Parameters in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to set recurring task parameters in Microsoft Project using Aspose.Tasks for .NET. Comprehensive tutorial with step-by-step guide.
type: docs
weight: 14
url: /net/rate-recurring-tasks/recurring-task-parameters/
---
## Introduction
In this tutorial, we will guide you through the process of setting Microsoft Project recurring task parameters using Aspose.Tasks for .NET.
## Prerequisites
Before you begin, ensure you have the following:
1. Basic understanding of C# programming language.
2. Installed Visual Studio or any other C# IDE.
3. Aspose.Tasks for .NET library installed and referenced in your project.

## Import Namespaces
Firstly, you need to import the necessary namespaces in your C# code:
```csharp
using System;
using NUnit.Framework;
```
## Step 1: Define the Document Directory
```csharp
String DataDir = "Your Document Directory";
```
Replace `"Your Document Directory"` with the path to your document directory.
## Step 2: Load the Project File
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
This line of code loads the Microsoft Project file into the `project` variable.
## Step 3: Define Recurring Task Parameters
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Here, you define the parameters for the recurring task such as task name, duration, recurrence pattern, recurrence range, and whether to ignore the resource calendar.
## Step 4: Set Calendar for Recurring Task
```csharp
parameters.SetCalendar(project, "Standard");
```
This step sets the calendar for the recurring task. In this example, it sets the calendar to "Standard".
## Step 5: Add Parameters to Project
```csharp
project.RootTask.Children.Add(parameters);
```
Finally, add the parameters to the project's root task.

## Conclusion
In this tutorial, we've demonstrated how to set Microsoft Project recurring task parameters using Aspose.Tasks for .NET. By following these steps, you can efficiently manage recurring tasks in your projects.
## FAQs
### Can I customize the recurrence pattern further?
Yes, Aspose.Tasks provides various recurrence patterns and options to customize according to your project requirements.
### Is there a trial version available before purchasing?
Yes, you can download a free trial from the Aspose.Tasks [website](https://purchase.aspose.com/buy) to evaluate the library's features.
### Does Aspose.Tasks support other project file formats?
Yes, Aspose.Tasks supports various project file formats including MPP, XML, XLSX, and more.
### Can I get support if I encounter any issues during implementation?
Yes, you can visit the Aspose.Tasks forum for assistance from the community or contact support for direct help.
### How can I obtain a temporary license for Aspose.Tasks?
You can obtain a temporary license from the [website](https://purchase.aspose.com/temporary-license/) for testing purposes.

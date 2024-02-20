---
title: Handling Monthly Recurrence Patterns in Aspose.Tasks
linktitle: Handling Monthly Recurrence Patterns in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to handle monthly recurrence patterns in Aspose.Tasks for .NET with this step-by-step tutorial.
type: docs
weight: 18
url: /net/advanced-concepts/monthly-recurrence-patterns/
---
## Introduction

Aspose.Tasks for .NET is a powerful API that allows developers to manipulate Microsoft Project files programmatically. One of the essential functionalities it offers is the ability to handle recurring tasks efficiently. In this tutorial, we'll delve into how to work with monthly recurrence patterns using Aspose.Tasks, step by step.

## Prerequisites

Before we begin, ensure you have the following prerequisites installed:

## Import Namespaces

First, make sure you have imported the necessary namespaces in your .NET project:

```csharp
using System;
using NUnit.Framework;
using Saving;
```

Now, let's break down the process of handling monthly recurrence patterns into multiple steps:

## Step 1: Initialize the Project

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Step 2: Set Recurring Task Parameters

Define the parameters for the recurring task, including the task name, duration, and recurrence pattern:

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

## Step 3: Add Parameters to the Project

```csharp
project.RootTask.Children.Add(parameters);
```

## Step 4: Save the Project

Save the modified project with the recurring task:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Conclusion

Handling monthly recurrence patterns in Aspose.Tasks for .NET is straightforward and efficient. By following the steps outlined in this tutorial, you can easily create recurring tasks with specific monthly intervals and recurrence ranges.

## FAQ's

### Q1: Is Aspose.Tasks compatible with all versions of Microsoft Project files?

A1: Aspose.Tasks supports various versions of Microsoft Project files, including MPP, MPT, XML, and MPX.

### Q2: Can I customize the recurrence pattern further?

A2: Yes, Aspose.Tasks provides extensive options for customizing recurrence patterns, including daily, weekly, monthly, and yearly.

### Q3: Is there a free trial available for Aspose.Tasks?

A3: Yes, you can obtain a free trial of Aspose.Tasks from the website [here](https://releases.aspose.com/).

### Q4: How can I get support for Aspose.Tasks?

A4: You can seek assistance and participate in discussions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Where can I purchase a license for Aspose.Tasks?

A5: You can purchase a license for Aspose.Tasks from the website [here](https://purchase.aspose.com/buy)

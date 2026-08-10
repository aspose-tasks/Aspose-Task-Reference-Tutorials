---
title: How to Set Recurrence in Aspose.Tasks (Month, Week, Day)
linktitle: Repetition by Month Week Day in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to set recurrence in Aspose.Tasks for .NET, add recurring task and automate recurring tasks by month, week, and day.
weight: 26
url: /net/advanced-features/repetition-by-month-week-day/
date: 2026-04-01
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set Recurrence in Aspose.Tasks (Month, Week, Day)

## Introduction

If you need to **how to set recurrence** for tasks in a project, Aspose.Tasks for .NET gives you a clean, programmatic way to add recurring task definitions that run by month, week, or day. In this tutorial we’ll walk through a real‑world example that shows you how to **add recurring task** entries, **automate recurring tasks**, and manage them directly from C# code. By the end, you’ll be ready to integrate this capability into any scheduling or project‑management solution.

## Quick Answers
- **What does “recurrence” mean in Aspose.Tasks?** It defines a pattern (daily, weekly, monthly) that automatically creates task instances over a date range.  
- **Which primary method creates the recurrence?** `RecurringTaskParameters` combined with a specific `RecurrencePattern`.  
- **Do I need a license to run this code?** A trial works for evaluation; a commercial license is required for production.  
- **Can I schedule weekly tasks instead of monthly?** Yes – swap `MonthlyRecurrencePattern` with `WeeklyRecurrencePattern`.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 and later.

## What Is Recurrence in Aspose.Tasks?

Recurrence is a set of rules that tells Aspose.Tasks to generate task instances at regular intervals—daily, weekly, or monthly—without manually duplicating them. This feature is essential for projects that contain routine activities such as status meetings, inspections, or maintenance work.

## Why Use Recurrence Features?

- **Save time:** No need to copy‑paste tasks manually.  
- **Reduce errors:** The library guarantees consistent dates and durations.  
- **Flexibility:** Combine patterns (e.g., “first Sunday of every 2 months”).  
- **Automation:** Perfect for generating schedules in CI pipelines or reporting tools.

## Prerequisites

Before we start, make sure you have:

1. **Basic Understanding of C#** – you’ll be writing a few lines of C# code.  
2. **Aspose.Tasks for .NET installed** – grab it from the [download page](https://releases.aspose.com/tasks/net/).  
3. **A .mpp project file** – we’ll use `Project1.mpp` as the source file.

## Import Namespaces

To begin, import the required Aspose.Tasks namespaces:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Step 1: Load the Project File

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

We create a `Project` instance that points to an existing Microsoft Project file.

### Step 2: Define Recurring Task Parameters

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

Here we **create recurring task** parameters:

- **TaskName** – the name of the generated task.  
- **Duration** – how long each occurrence lasts.  
- **RecurrencePattern** – a monthly pattern that repeats every 2 months on the first Sunday.  
- **RecurrenceRange** – the start and end dates that bound the schedule.

### Step 3: Add the Recurring Task to the Project

```csharp
project.RootTask.Children.Add(parameters);
```

This line **adds the recurring task** to the root of the project hierarchy.

### Step 4: Save the Updated Project

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

The project is saved as a new `.mpp` file that now contains the automated schedule.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **Task not appearing** | Recurrence range is outside the project dates. | Verify `Start` and `Finish` values are within the project calendar. |
| **Wrong weekday** | `WeekDay` enum mismatch. | Use `DayOfWeek.Monday` … `DayOfWeek.Sunday` as needed. |
| **License exception** | Running without a valid license in production. | Apply a temporary or full license before saving. |

## Frequently Asked Questions

### Q1: Can I customize the recurrence pattern beyond the provided examples?

A1: Yes, Aspose.Tasks for .NET offers extensive customization options for recurrence patterns, allowing you to tailor them to your specific requirements.

### Q2: Is there a trial version available for Aspose.Tasks for .NET?

A2: Yes, you can obtain a free trial of Aspose.Tasks for .NET from the [releases page](https://releases.aspose.com/).

### Q3: How can I obtain support for Aspose.Tasks for .NET?

A3: You can seek assistance and engage with the community on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q4: Are temporary licenses available for Aspose.Tasks for .NET?

A4: Yes, you can acquire temporary licenses from the [purchase page](https://purchase.aspose.com/temporary-license/) for testing and evaluation purposes.

### Q5: Where can I find comprehensive documentation for Aspose.Tasks for .NET?

A5: You can refer to the detailed [documentation](https://reference.aspose.com/tasks/net/) available on the Aspose website for in-depth guidance on utilizing the library.

---

**Last Updated:** 2026-04-01  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
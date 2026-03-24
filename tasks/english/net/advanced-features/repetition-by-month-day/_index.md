---
title: Manage Recurring Tasks: Repetition by Month Day in Aspose.Tasks
linktitle: Repetition by Month Day in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage recurring tasks and create recurring task schedules in .NET projects with Aspose.Tasks. Step-by-step guide for handling repetition by month day.
weight: 25
url: /net/advanced-features/repetition-by-month-day/
date: 2026-03-24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manage Recurring Tasks: Repetition by Month Day

## Introduction

If you need to **manage recurring tasks** in a .NET project, Aspose.Tasks gives you a clean, programmatic way to define monthly repetitions such as “the first Monday of every other month.” In this tutorial we’ll walk through a real‑world example that shows how to create a recurring task, define its recurrence pattern, add it to a project, and finally save the project as an MPP file.

## Quick Answers
- **What does “manage recurring tasks” mean?** It means defining tasks that automatically repeat on a schedule without manual duplication.  
- **Which API class creates a recurring task?** `RecurringTaskParameters`.  
- **How to save the project after adding a recurrence?** Use `Project.Save(..., SaveFileFormat.Mpp)`.  
- **Can I set a custom start‑date and end‑date?** Yes, via `EndByRecurrenceRange`.  
- **Is a license required for production?** Yes, a valid Aspose.Tasks license is needed for non‑trial use.

## Prerequisites

Before you start, make sure you have:

1. **Basic C# knowledge** – you should be comfortable with classes and objects.  
2. **Aspose.Tasks for .NET installed** – download it from [here](https://releases.aspose.com/tasks/net/).  
3. **Visual Studio (or another IDE)** – to compile and run the sample code.

## Import Namespaces

In your C# project, import the namespaces that expose the Aspose.Tasks API:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## How to Create Recurring Task with Monthly Repetition

### Step 1: Load the Project File

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

This line creates a `Project` instance and loads an existing MPP file named **Project1.mpp**.

### Step 2: Define Recurrence Pattern

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

Here we **create recurring task** parameters:

* **TaskName** – the name that will appear in the Gantt chart.  
* **Duration** – set to one day.  
* **RecurrencePattern** – a `MonthlyRecurrencePattern` that repeats every 2 months on the first day of the month (`DayPosition = 1`).  
* **RecurrenceRange** – defines the start and finish dates for the series.

### Step 3: Add Recurrence to the Project

```csharp
project.RootTask.Children.Add(parameters);
```

This line **adds the recurrence** to the root of the project hierarchy.

### Step 4: How to Save MPP File

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

After the task is added, we **save the project** using the `Save` method. The file is stored as an MPP file that can be opened in Microsoft Project.

## Why Use Aspose.Tasks for Recurring Tasks?

* **Full control** – you decide the interval, day position, and date range programmatically.  
* **No UI limitations** – unlike the Project UI, the API lets you automate complex schedules.  
* **Cross‑platform** – works with .NET Framework, .NET Core, and .NET 5/6.

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **Incorrect start date** | Verify that the `Start` property uses the correct `DateTime` (including time). |
| **Task not appearing in Gantt** | Ensure the project is saved after adding the recurrence and that you open the saved file. |
| **License exception** | Load a valid Aspose.Tasks license before creating the `Project` instance. |

## Frequently Asked Questions

**Q: Is Aspose.Tasks compatible with all versions of .NET?**  
A: Aspose.Tasks supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6.

**Q: Can I customize the recurrence pattern further?**  
A: Yes, you can use other recurrence classes like `WeeklyRecurrencePattern` or adjust `ByMonthDayRepetition` properties.

**Q: Does Aspose.Tasks provide support for other project management functionalities?**  
A: Absolutely, it includes task tracking, resource allocation, and Gantt chart generation.

**Q: Is there a trial version available for Aspose.Tasks?**  
A: Yes, you can avail of a free trial from [here](https://releases.aspose.com/) to explore Aspose.Tasks' capabilities before making a purchase decision.

**Q: Where can I seek assistance if I encounter issues or have queries?**  
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to seek support from the community or the Aspose team.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

---
---
title: How to Create Monthly Recurring Task in Aspose.Tasks
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to create monthly recurring task in Aspose.Tasks for .NET with this step‑by‑step tutorial.
weight: 18
url: /net/advanced-concepts/monthly-recurrence-patterns/
date: 2026-03-08
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Monthly Recurring Task Using Aspose.Tasks

## Introduction

Aspose.Tasks for .NET lets you programmatically manipulate Microsoft Project files, and one of the most common real‑world needs is to **create monthly recurring task** schedules. Whether you’re building a project‑tracking tool, automating resource allocation, or generating recurring maintenance work items, this tutorial walks you through the exact steps to add a monthly recurrence pattern to a task.

In the next sections you’ll see how to set up the project, define the recurrence parameters, and finally save the updated file—all with clear explanations and practical tips.

## Quick Answers
- **What does “monthly recurring task” mean?** A task that repeats on a defined day‑or‑week pattern every month.  
- **Which API class handles recurrence?** `RecurringTaskParameters` together with `MonthlyRecurrencePattern`.  
- **Do I need a license to run the sample?** A free trial works for evaluation; a license is required for production.  
- **Can I change the interval?** Yes – set `RepetitionInterval` to the number of months between occurrences.  
- **What file formats are supported?** Both `.mpp` and `.xml` Project files can be loaded and saved.

## What is a Monthly Recurrence Pattern?

A monthly recurrence pattern tells Microsoft Project (and Aspose.Tasks) how often a task should repeat each month. You can specify a fixed day of the month (e.g., the 1st) or a relative position (e.g., the last Friday). The API translates these rules into the underlying Project file structure.

## Why use Aspose.Tasks for this?

- **Full control** – No UI limitations; you define every aspect of the pattern in code.  
- **Cross‑platform** – Works on .NET Framework, .NET Core, and .NET 5/6+.  
- **No Microsoft Project required** – Generate or modify files on a server or CI pipeline.  

## Prerequisites

Before you start, make sure you have:

- .NET 6 (or .NET 5/Framework 4.7+) installed.  
- Aspose.Tasks for .NET NuGet package added to your project.  
- A sample Project file (`Project1.mpp`) placed in a known folder (`DataDir`).  

## Import Namespaces

First, import the namespaces required for working with tasks and saving projects:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Step 1: Initialize the Project

Create a `Project` instance that points to your existing `.mpp` file. This loads the file into memory so you can modify it.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Pro tip:** If the file does not exist, Aspose.Tasks will create a new blank project automatically.

## Step 2: Set Recurring Task Parameters

Define the details of the recurring task, including its name, duration, and the monthly pattern you want to apply.

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

- `DayPosition = 1` means the task occurs on the **first day** of the month.  
- `RepetitionInterval = 2` makes the task repeat **every two months**.  
- `Start` and `Finish` define the overall window during which the recurrence is active.

## Step 3: Add Parameters to the Project

Attach the `RecurringTaskParameters` object to the root task’s children collection. This effectively creates the recurring task in the project hierarchy.

```csharp
project.RootTask.Children.Add(parameters);
```

## Step 4: Save the Project

Persist the changes by saving the project to a new file. You can choose any supported format; here we use the native `.mpp` format.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

After running the code, open the resulting file in Microsoft Project to see the monthly recurring task you just created.

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| Task does not appear after saving | Project not refreshed in UI | Re‑open the file or call `project.UpdateTaskLinks()` before saving. |
| Wrong start date | `Start` set to a weekend | Use `DateTime` that falls on a working day or adjust the calendar. |
| Recurrence interval ignored | Using `ByMonthDayRepetition` with `DayPosition` = 0 | Ensure `DayPosition` is 1‑31. |

## Conclusion

By following these steps you now know how to **create monthly recurring task** schedules with Aspose.Tasks for .NET. The API gives you granular control over recurrence intervals, start/finish ranges, and the specific day pattern, enabling you to automate complex project planning scenarios.

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

## Frequently Asked Questions

**Q: Can I use this code in a .NET Core application?**  
A: Absolutely. Aspose.Tasks for .NET fully supports .NET Core 3.1 and later versions.

**Q: How do I change the recurrence to “last weekday of the month”?**  
A: Use `ByMonthDayRepetition` with `DayPosition = -1` (negative values count from the end of the month) and set `WeekDay` accordingly.

**Q: What happens if the recurrence range exceeds the project’s calendar?**  
A: The API respects the project calendar; occurrences falling on non‑working days are either skipped or moved based on the calendar’s settings.

**Q: Is it possible to delete a specific occurrence of a recurring task?**  
A: Yes. After adding the recurring task, you can retrieve individual occurrences via `Task.GetOccurrences()` and delete the ones you don’t need.

**Q: Does Aspose.Tasks handle timezone differences automatically?**  
A: The library stores dates in UTC; you can convert to local time using standard .NET `DateTime` methods if needed.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
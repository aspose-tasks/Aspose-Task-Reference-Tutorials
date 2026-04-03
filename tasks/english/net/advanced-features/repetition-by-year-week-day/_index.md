---
title: How to Use Aspose.Tasks – Repetition by Year Week Day
linktitle: Repetition by Year Week Day in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to use Aspose.Tasks to add recurring task project and save project as MPP. This guide shows the Repetition by Year Week Day feature step‑by‑step.
weight: 28
url: /net/advanced-features/repetition-by-year-week-day/
date: 2026-04-03
keywords:
  - how to use aspose.tasks
  - add recurring task project
  - save project as mpp
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Repetition by Year Week Day in Aspose.Tasks

## Introduction

When you need to **how to use Aspose.Tasks** for handling complex recurring schedules, the library gives you fine‑grained control over yearly patterns. In this tutorial we’ll walk through creating a task that repeats on a specific weekday of a particular month, spanning multiple years. By the end you’ll be able to **add recurring task project** entries and **save project as MPP** with just a few lines of C#.

## Quick Answers
- **What does “Repetition by Year Week Day” mean?** It repeats a task on a chosen weekday (e.g., first Sunday) of a given month each year.  
- **Which .NET versions are supported?** All modern .NET Framework and .NET Core/5/6 versions.  
- **Do I need a license to run the code?** A free trial works for development; a commercial license is required for production.  
- **Can I change the recurrence range?** Yes – you can set a start date, end date, or a fixed number of occurrences.  
- **Is the output an MPP file?** Absolutely – the project is saved as an MPP file ready for Microsoft Project.

## What is the “Repetition by Year Week Day” feature?

The feature lets you define a yearly recurrence that targets a particular **day of the week** (e.g., Sunday) and a **position** within the month (first, second, last, etc.). This is ideal for tasks like quarterly reviews, annual audits, or any event that follows a calendar‑based rhythm.

## Why use Aspose.Tasks for recurring tasks?

- **Precision** – Full control over months, weekdays, and ordinal positions.  
- **Compatibility** – Generates native MPP files that open flawlessly in Microsoft Project.  
- **No COM interop** – Pure .NET API, no need for Office installations.  
- **Scalability** – Works for small projects and enterprise‑level schedules alike.

## Prerequisites

Before diving into the code, make sure you have:

1. **Basic .NET knowledge** – Familiarity with C# and object‑oriented concepts.  
2. **Aspose.Tasks for .NET** – Download it from the [download link](https://releases.aspose.com/tasks/net/) and add the DLL to your project.  
3. **Access to the official docs** – The [documentation](https://reference.aspose.com/tasks/net/) contains exhaustive details on all classes.  
4. **A development IDE** – Visual Studio, Rider, or any compatible .NET editor.

Now that you’re set, let’s see the implementation.

## How to Use Aspose.Tasks for Recurring Tasks

### Importing Necessary Namespaces

First, bring the required namespaces into scope so you can work with projects, tasks, and saving options.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Step 1: Initialize Project and Task Parameters

Create a new `Project` instance, then define a `RecurringTaskParameters` object that describes the recurrence pattern.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Adjust `Month`, `WeekDay`, and `Position` to match your real‑world schedule.

### Step 2: Add Parameters to Project

Insert the recurring task definition into the root of the project.

```csharp
project.RootTask.Children.Add(parameters);
```

### Step 3: Save Project as MPP

Finally, persist the project to an MPP file so it can be opened in Microsoft Project or any compatible viewer.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> This demonstrates **save project as mpp** in a single line of code.

## Common Issues and Solutions

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| No tasks appear after opening the MPP file | Recurrence range dates are outside the project calendar | Verify `Start` and `Finish` dates fall within the project's working time |
| Exception `ArgumentNullException` on `Add` | `parameters` is null or not fully initialized | Ensure all required properties (TaskName, Duration, RecurrencePattern) are set |
| Wrong weekday selected | `WeekDay` enum value mismatch | Use `DayOfWeek.Monday` … `DayOfWeek.Sunday` as needed |

## Frequently Asked Questions

**Q: Can I customize the recurrence pattern beyond the provided example?**  
A: Yes, Aspose.Tasks lets you combine `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern`, or even custom `RecurrenceRange` objects to fit any schedule.

**Q: Is Aspose.Tasks for .NET compatible with other project management software?**  
A: Absolutely – the library reads and writes MPP, XML, and Primavera formats, enabling smooth data exchange.

**Q: How can I handle exceptions or modifications to recurring tasks?**  
A: Use the `ExceptionTask` class to create overrides for specific occurrences, or edit the `RecurringTaskParameters` and re‑save the project.

**Q: Does Aspose.Tasks support cloud‑based solutions?**  
A: Yes, you can run the API in Azure Functions, AWS Lambda, or any .NET‑compatible cloud service.

**Q: Is there a trial version available for Aspose.Tasks for .NET?**  
A: Yes, you can access a free trial of Aspose.Tasks for .NET from the [website](https://releases.aspose.com/), allowing you to explore its features before making a purchase decision.

**Q: How do I add a recurring task to an existing project without overwriting other data?**  
A: Load the existing project with `new Project("Existing.mpp")`, add the `RecurringTaskParameters` to `RootTask.Children`, and then `Save` the file.

## Conclusion

By mastering **how to use Aspose.Tasks** for the **Repetition by Year Week Day** scenario, you gain the ability to **add recurring task project** entries that align perfectly with real‑world calendars and **save project as MPP** for seamless collaboration. Incorporate these snippets into your own solutions to boost scheduling accuracy and reduce manual effort.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
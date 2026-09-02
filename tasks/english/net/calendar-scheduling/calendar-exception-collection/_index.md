---
title: Set Standard Calendar and Handle Exceptions in Aspose.Tasks
linktitle: Set Standard Calendar and Handle Exceptions in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to set standard calendar and manage project holidays in your .NET projects using Aspose.Tasks for accurate scheduling.
date: 2026-04-09
weight: 13
url: /net/calendar-scheduling/calendar-exception-collection/
keywords:
- set standard calendar
- manage project holidays
- load project calendar
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Standard Calendar and Handle Exceptions in Aspose.Tasks

## Introduction

Accurate scheduling is the backbone of any successful project, and real‑world plans often need to deviate from the default work calendar because of holidays, special events, or unexpected shutdowns. Aspose.Tasks for .NET makes it easy to **set standard calendar** settings and then layer custom exceptions on top. In this tutorial you’ll learn how to load a project calendar, set a standard calendar, and manage project holidays through the Calendar Exception Collection feature.

## Quick Answers
- **What does “set standard calendar” do?** It resets a calendar to the default working time (9 AM‑5 PM, Monday‑Friday) before you add custom exceptions.  
- **Which method clears existing exceptions?** `Calendar.Exceptions.Clear()` removes all previously defined exceptions.  
- **How can I add a holiday?** Create a `CalendarException` with `DayWorking = false` and add it to the collection.  
- **Do I need to reload the project after changes?** No, changes are applied directly to the in‑memory `Project` object.  
- **What libraries are required?** Aspose.Tasks for .NET (any supported .NET version) and `System` namespaces.

## Prerequisites

Before diving into the code, make sure you have:

1. **Aspose.Tasks for .NET** – download it [here](https://releases.aspose.com/tasks/net/).  
2. Basic knowledge of **C#** – you’ll be writing a few short snippets.  
3. A development environment such as **Visual Studio** or **JetBrains Rider**.

## Import Namespaces

These `using` directives give you access to the classes needed for calendar manipulation.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## What is a Calendar Exception?

A *calendar exception* represents a period where the normal working schedule is altered – for example, a company‑wide holiday or a temporary overtime schedule. By adding exceptions to a calendar you can model real‑world constraints without changing the base calendar.

## How to Set Standard Calendar in Aspose.Tasks

The first step is to load your project file and retrieve the calendar you want to work with.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Step 1: Clear Existing Exceptions and Reset to a Standard Calendar

Before adding new rules, it’s a good practice to clear any old exceptions and **set standard calendar** settings. This ensures a clean baseline.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Step 2: Define a Working‑Time Exception

Sometimes you need to create a temporary schedule (e.g., extended hours for a product launch). The following snippet defines a working‑time exception that spans several days and includes two daily work periods.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Step 3: Add Non‑Working Time Exceptions (Holidays)

To **manage project holidays**, create exceptions where `DayWorking` is `false`. The example below adds a two‑day holiday block.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Step 4: Display Calendar Exceptions (Verification)

After adding exceptions, you’ll often want to verify that they were recorded correctly. The following loop prints each exception’s details to the console.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Step 5: Remove All Exceptions (Cleanup)

If you need to revert the calendar back to its original state, you can remove every exception programmatically.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| Exceptions not appearing after saving | Project not saved after modifications | Call `project.Save("output.mpp")` after making changes. |
| Overlapping exceptions cause unexpected work hours | Aspose.Tasks uses the last added exception for overlapping periods | Order your `Add` calls carefully or adjust priorities manually. |
| `MakeStandardCalendar` resets custom working times | It intentionally clears custom times; re‑add them after the call if needed. | Add your custom `WorkingTime` objects after invoking `MakeStandardCalendar`. |

## Frequently Asked Questions

**Q: Can I add multiple exceptions to a single calendar?**  
A: Yes, you can add multiple exceptions to a calendar using the `AddRange` method.

**Q: How do I handle recurring exceptions, such as weekly holidays?**  
A: You can programmatically calculate recurring exceptions and add them to the calendar using custom logic.

**Q: Is it possible to import calendar exceptions from external sources?**  
A: Yes, you can read calendar exceptions from external sources like databases or CSV files and integrate them into your project.

**Q: What happens if there are overlapping exceptions in the calendar?**  
A: Aspose.Tasks for .NET allows you to handle overlapping exceptions by defining priorities or resolving conflicts based on your project requirements.

**Q: Can I customize the working times for each day within an exception?**  
A: Yes, you can specify custom working times for individual days within an exception to accommodate specific scheduling needs.

## Conclusion

By **setting a standard calendar** first and then layering custom exceptions, you gain full control over project scheduling, making it easy to **manage project holidays** and any other special‑case timelines. The Calendar Exception Collection in Aspose.Tasks provides a clean, programmatic way to model real‑world calendars directly within your .NET applications.

---

**Last Updated:** 2026-04-09  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: "Project Management Task Scheduling with Year Day Repetition in Aspose.Tasks"
linktitle: Repetition by Year Day in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn project management task scheduling and how to add recurring task using Aspose.Tasks for .NET, including saving project as MPP.
date: 2026-04-03
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
weight: 27
url: /net/advanced-features/repetition-by-year-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Project Management Task Scheduling with Year Day Repetition in Aspose.Tasks

## Introduction

Effective **project management task scheduling** is the backbone of any successful project. When tasks repeat on a yearly basis—such as annual audits, maintenance windows, or seasonal reviews—handling those recurrences manually can become error‑prone and time‑consuming. Aspose.Tasks for .NET simplifies this by letting you programmatically define year‑day patterns, so you can focus on what matters most: delivering value. In this tutorial you’ll learn **how to add recurring task** logic based on a specific day of the year and see exactly **how to save project as MPP** for seamless integration with Microsoft Project.

## Quick Answers
- **What does “year day repetition” mean?** It schedules a task on a specific day of a specific month each year.  
- **Which API class creates the recurrence?** `YearlyRecurrencePattern` combined with `ByYearDayRepetition`.  
- **Can I set a start and end date?** Yes, using `EndByRecurrenceRange`.  
- **What file format is produced?** The project is saved as an MPP file (`SaveFileFormat.Mpp`).  
- **Do I need a license for production?** A commercial license is required for non‑evaluation use.

## Prerequisites

Before diving into the tutorial, ensure that you have the following prerequisites in place:

1. Aspose.Tasks for .NET Library: Download and install the Aspose.Tasks for .NET library from the [website](https://releases.aspose.com/tasks/net/).  
2. Development Environment: Set up a suitable development environment with Visual Studio or any other preferred IDE for .NET development.  
3. Basic Knowledge of C#: Familiarize yourself with C# programming language fundamentals to follow along with the code examples.  
4. Project Management Concepts: Understanding of project management concepts and task scheduling will aid in grasping the tutorial concepts effectively.

## Import Namespaces

Before we begin coding, let's import the necessary namespaces to facilitate our task manipulation using Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Now, let's break down the provided example into multiple steps and elucidate each step in detail.

## How to Add Recurring Task with Year Day Pattern

### Step 1: Load Project File

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Here, we initialize a new `Project` object and load an existing project file named **Project1.mpp**.

### Step 2: Define Recurring Task Parameters

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

In this step, we define parameters for our recurring task. We specify the task name, duration, and recurrence pattern. For yearly recurrence, we use the `YearlyRecurrencePattern` and set the repetition to occur on the **1st day of July** using `ByYearDayRepetition`. Additionally, we define the recurrence range from July 1 2018 to July 1 2019.

### Step 3: Add Task to Project

```csharp
project.RootTask.Children.Add(parameters);
```

Here, we add the defined recurring task parameters to the root task of the project.

### Step 4: Save Project as MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Finally, we **save the project as an MPP file**, making it ready for opening in Microsoft Project or any compatible viewer.

## Why This Matters

- **Automation** – Eliminates manual entry of yearly tasks, reducing human error.  
- **Consistency** – Guarantees that the same day‑month pattern is applied across multiple years.  
- **Integration** – The resulting MPP file can be shared with stakeholders who rely on Microsoft Project.  

## Common Pitfalls & Tips

- **DateTime precision** – Ensure the start time aligns with your project calendar; otherwise, the task may appear offset.  
- **Time zones** – The API works with `DateTime` objects; consider UTC conversion if your application spans multiple regions.  
- **License enforcement** – In evaluation mode, the saved MPP may contain a watermark; use a valid license for production.

## Frequently Asked Questions

**Q: Can Aspose.Tasks handle complex recurrence patterns?**  
A: Yes, Aspose.Tasks provides comprehensive support for various recurrence patterns, including yearly, monthly, weekly, and daily repetitions.

**Q: Is Aspose.Tasks compatible with different project file formats?**  
A: Absolutely, Aspose.Tasks supports popular project file formats such as MPP, XML, and CSV, ensuring compatibility across different project management tools.

**Q: Does Aspose.Tasks offer documentation and support for developers?**  
A: Yes, developers can access extensive documentation and seek assistance from the Aspose.Tasks community forums for any queries or issues they encounter.

**Q: Can I customize task properties like duration and start date using Aspose.Tasks?**  
A: Certainly, Aspose.Tasks provides robust APIs to manipulate task properties dynamically, allowing developers to customize durations, start dates, dependencies, and more.

**Q: Is Aspose.Tasks suitable for both small‑scale and enterprise‑level projects?**  
A: Indeed, Aspose.Tasks is designed to cater to the needs of developers working on projects of all scales, from individual tasks to large‑scale enterprise projects.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
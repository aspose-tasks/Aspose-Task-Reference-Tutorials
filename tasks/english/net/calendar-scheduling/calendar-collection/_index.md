---
title: Set Working Hours in Aspose.Tasks Calendar Collection
linktitle: Managing Calendar Collection in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to set working hours and manage calendar collections in Aspose.Tasks for .NET. Import calendars Microsoft Project, remove calendar project, and get calendar by name easily.
weight: 11
url: /net/calendar-scheduling/calendar-collection/
date: 2026-04-13
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Working Hours in Aspose.Tasks Calendar Collection

In this tutorial, you'll learn how to **set working hours** and manage calendar collections using Aspose.Tasks for .NET. Calendars define workdays, holidays, and exceptions, so mastering them lets you control project schedules precisely. We'll also show you how to import calendars Microsoft Project, remove a calendar from a project, and get a calendar by name.

## Quick Answers
- **What is the primary class for calendars?** `Project.Calendars` collection.
- **How do I set working hours?** Create or modify a `Calendar` object and define its `WorkingTime`.
- **Can I import calendars from Microsoft Project?** Yes – load an MPP file and access its calendars.
- **How to remove a calendar from a project?** Use `Project.Calendars.Remove(calendar)`.
- **How to retrieve a calendar by name?** Call `Project.Calendars.GetByName("YourCalendar")`.

## Prerequisites

Before we begin, ensure you have the following:

1. Visual Studio: Install Visual Studio or any other compatible IDE for .NET development.  
2. Aspose.Tasks for .NET: Download and install Aspose.Tasks for .NET from [here](https://releases.aspose.com/tasks/net/).  
3. Basic understanding of C#: Familiarity with C# programming language will be beneficial.

## Import Namespaces

First, let's import the necessary namespaces to work with Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Creating a New Calendar

### Step 1: Initialize a new `Project` object.
```csharp
var project = new Project();
```

### Step 2: Add calendars to the project's calendar collection.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Step 3: Iterate through the calendars and display their names.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## How to Set Working Hours for a Calendar?

To **set working hours**, you modify the `WorkingTime` collection of a `Calendar`.  
For example, you can define a standard 9 am‑5 pm workday or add custom exceptions.  
The code for this is identical to the examples shown later when we create a standard calendar.

## Replacing a Calendar with a New Calendar

### Step 1: Load an existing project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Step 2: Remove the existing calendar (if it exists).  
This demonstrates the **remove calendar project** scenario.
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Step 3: Add a new calendar.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Getting Calendar by Name or ID

### Step 1: Load the project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Step 2: Retrieve calendars by name or UID.  
This illustrates the **get calendar by name** operation.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Step 3: Display calendar details.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Iterating Over Calendars

### Step 1: Load the project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Step 2: Retrieve the count of calendars.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Step 3: Iterate over the calendar collection and display names.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Making a Standard Calendar

### Step 1: Initialize a new project.
```csharp
var project = new Project();
```

### Step 2: Define a new calendar and make it standard.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Step 3: Save the project.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions

- **Calendar not found when using `GetByName`** – Ensure the exact name matches the case used when the calendar was added.  
- **Working hours not applied** – After setting `WorkingTime`, remember to save the project; otherwise changes remain in memory only.  
- **Importing calendars from an MPP file fails** – Verify that the source file is a valid Microsoft Project file and that you have read permissions.

## FAQ's

### Q1: Can I create custom workdays in Aspose.Tasks?

A1: Yes, you can create custom workdays by adding exceptions to calendars.

### Q2: Is it possible to import calendars from Microsoft Project files?

A2: Absolutely, Aspose.Tasks supports importing calendars from Microsoft Project files.

### Q3: How can I remove a specific calendar from a project?

A3: You can remove a calendar by getting it from the collection and then calling the `Remove` method.

### Q4: Does Aspose.Tasks support exporting calendars to different formats?

A4: Yes, Aspose.Tasks allows exporting calendars to various formats like XML, MPP, etc.

### Q5: Can I customize working hours for specific days in a calendar?

A5: Certainly, you can define working hours for individual days using exceptions in the calendar.

## Frequently Asked Questions

**Q: What is the best way to set a 24‑hour shift calendar?**  
A: Create a new calendar, clear existing `WorkingTime` entries, and add a single `WorkingTime` range from 00:00 to 24:00 for each weekday.

**Q: Can I copy a calendar from one project to another?**  
A: Yes—export the calendar to XML using `project.Save` and then import it into another project with `new Project(xmlPath)`.

**Q: How do I programmatically import calendars Microsoft Project?**  
A: Load the MPP file with `new Project("source.mpp")`; the calendars become available via `project.Calendars`.

**Q: Is there a limit to the number of calendars in a project?**  
A: Practically no; the collection can hold as many calendars as memory allows, but keep the list manageable for performance.

**Q: Do changes to a calendar automatically update tasks that use it?**  
A: Yes—tasks linked to a calendar reflect the updated working times after you save the project.

---

**Last Updated:** 2026-04-13  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
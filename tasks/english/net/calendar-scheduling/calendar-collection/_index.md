---
title: Managing Calendar Collection in Aspose.Tasks
linktitle: Managing Calendar Collection in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage calendar collections in Aspose.Tasks for .NET efficiently. Create, modify, and manipulate calendars with ease.
weight: 11
url: /net/calendar-scheduling/calendar-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Managing Calendar Collection in Aspose.Tasks

## Introduction

In this tutorial, we'll explore how to manage calendar collections in Aspose.Tasks for .NET. Calendars play a crucial role in project management, defining workdays, holidays, and exceptions. Aspose.Tasks provides robust functionality to manipulate calendars within your projects.

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

## Replacing a Calendar with a New Calendar

### Step 1: Load an existing project.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Step 2: Remove the existing calendar (if exists).
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

## Conclusion

Managing calendar collections in Aspose.Tasks for .NET is essential for effective project management. With the provided functionalities, you can efficiently create, modify, and manipulate calendars according to your project requirements.

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

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

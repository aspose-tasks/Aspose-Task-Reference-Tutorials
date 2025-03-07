---
title: Repetition by Year Day in Aspose.Tasks
linktitle: Repetition by Year Day in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to handle year day repetitions in Aspose.Tasks for .NET to streamline recurring task management efficiently.
weight: 27
url: /net/advanced-features/repetition-by-year-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Repetition by Year Day in Aspose.Tasks

## Introduction

In the realm of project management, efficient task scheduling and recurrence play pivotal roles in ensuring timely execution and smooth workflow. Aspose.Tasks for .NET offers a robust solution for developers to handle recurring tasks effortlessly within their applications. In this tutorial, we delve into the intricacies of working with year day repetitions using Aspose.Tasks, providing a comprehensive guide for creating recurring tasks based on yearly patterns.

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

## Step 1: Load Project File

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Here, we initialize a new `Project` object and load an existing project file named "Project1.mpp".

## Step 2: Define Recurring Task Parameters

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

In this step, we define parameters for our recurring task. We specify the task name, duration, and recurrence pattern. For yearly recurrence, we use the `YearlyRecurrencePattern` and set the repetition to occur on the 1st day of July using `ByYearDayRepetition`. Additionally, we define the recurrence range from July 1, 2018, to July 1, 2019.

## Step 3: Add Task to Project

```csharp
project.RootTask.Children.Add(parameters);
```

Here, we add the defined recurring task parameters to the root task of the project.

## Step 4: Save Project

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Finally, we save the modified project file with the added recurring task.

## Conclusion

In this tutorial, we've explored the process of working with year day repetitions in Aspose.Tasks for .NET. By following the provided steps, developers can seamlessly integrate recurring task functionality into their applications, enhancing project management capabilities.

## FAQ's

### Q1: Can Aspose.Tasks handle complex recurrence patterns?

A1: Yes, Aspose.Tasks provides comprehensive support for various recurrence patterns, including complex ones like yearly, monthly, weekly, and daily repetitions.

### Q2: Is Aspose.Tasks compatible with different project file formats?

A2: Absolutely, Aspose.Tasks supports popular project file formats such as MPP, XML, and CSV, ensuring compatibility across different project management tools.

### Q3: Does Aspose.Tasks offer documentation and support for developers?

A3: Yes, developers can access extensive documentation and seek assistance from the Aspose.Tasks community forums for any queries or issues they encounter.

### Q4: Can I customize task properties like duration and start date using Aspose.Tasks?

A4: Certainly, Aspose.Tasks provides robust APIs to manipulate task properties dynamically, allowing developers to customize durations, start dates, dependencies, and more.

### Q5: Is Aspose.Tasks suitable for both small-scale and enterprise-level projects?

A5: Indeed, Aspose.Tasks is designed to cater to the needs of developers working on projects of all scales, from individual tasks to large-scale enterprise projects.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

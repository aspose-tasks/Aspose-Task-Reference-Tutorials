---
title: Calculation Type in Aspose.Tasks
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to customize value calculations in .NET projects with Calculation Type in Aspose.Tasks library.
type: docs
weight: 30
url: /net/advanced-features/calculation-type/
---
## Introduction

In this tutorial, we'll explore the Calculation Type feature in Aspose.Tasks for .NET. Aspose.Tasks is a powerful library that enables .NET developers to work with Microsoft Project files without the need for Microsoft Project installed on their systems. Calculation Type allows us to define how values are calculated for tasks and summary tasks within a project.

## Prerequisites

Before we begin, ensure that you have the following prerequisites:

1. Basic knowledge of C# and .NET framework.
2. Visual Studio installed on your system.
3. Aspose.Tasks for .NET library installed. You can download it from [here](https://releases.aspose.com/tasks/net/).
4. Access to Aspose.Tasks for .NET documentation for reference, available [here](https://reference.aspose.com/tasks/net/).

## Import Namespaces

Before diving into the example, make sure to import the necessary namespaces:

```csharp
using System;
using NUnit.Framework;

```

## Step 1: Create a new Project

First, let's create a new project object:

```csharp
var project = new Project();
```

## Step 2: Add a Task

Now, let's add a task to our project:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Step 3: Define Calculation Type for an Extended Attribute

We'll create an extended attribute definition with the Calculation Type set to Formula:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Step 4: Define Calculation Type for Summary Rows

Next, we'll create another extended attribute definition where values for summary tasks are calculated using the Average rollup type:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Conclusion

In this tutorial, we've explored how to work with Calculation Type in Aspose.Tasks for .NET. By defining Calculation Types for extended attributes, we can customize how values are calculated for tasks and summary tasks within a project, providing greater flexibility and control.

## FAQ's

### Q1: What is Calculation Type in Aspose.Tasks?

A1: Calculation Type in Aspose.Tasks determines how values are calculated for tasks and summary tasks within a project, offering options such as Formula and Rollup.

### Q2: How do I set Calculation Type for an Extended Attribute?

A2: You can set Calculation Type for an Extended Attribute by defining its CalculationType property accordingly.

### Q3: Can I customize Calculation Type for summary rows in a project?

A3: Yes, Aspose.Tasks allows you to specify Calculation Type for summary rows, enabling you to tailor value calculations based on your requirements.

### Q4: Are there different Rollup Types available for summary task calculations?

A4: Yes, Aspose.Tasks provides various Rollup Types such as Average, Sum, and Count for calculating values of summary tasks.

### Q5: Where can I find more resources on Aspose.Tasks for .NET?

A5: You can explore the documentation and community support forums available on the [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) for comprehensive guidance and assistance.

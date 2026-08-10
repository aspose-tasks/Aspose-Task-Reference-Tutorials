---
title: How to Set Calculation Type in Aspose.Tasks
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to set calculation in Aspose.Tasks for .NET, with examples to calculate summary values, define calculation formula, and configure rollup summary.
weight: 30
url: /net/advanced-features/calculation-type/
date: 2026-03-24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set Calculation Type in Aspose.Tasks

## Introduction

If you need to **how to set calculation** rules for tasks and summary rows in a Microsoft Project file, this tutorial shows you exactly that using Aspose.Tasks for .NET. We'll walk through a complete **calculation type example**, demonstrate how to **calculate summary values**, and explain how to **define calculation formula** and **configure rollup summary** for extended attributes. By the end, you’ll be able to add a task to a project, set custom calculation logic, and control roll‑up behavior with confidence.

## Quick Answers
- **What is the primary purpose?** To control how task and summary values are computed in a Project file.  
- **Which API class is used?** `ExtendedAttributeDefinition` together with `CalculationType` and `SummaryRowsCalculationType`.  
- **Can I use a formula?** Yes – set `CalculationType = CalculationType.Formula` and provide a formula string.  
- **How do I roll‑up summary values?** Use `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` and specify a `RollupType` such as `Average`.  
- **Do I need a license?** A valid Aspose.Tasks license is required for production use.

## What is Calculation Type and how to set calculation?

`CalculationType` tells Aspose.Tasks how to compute the value of an extended attribute. You can choose a static value, a formula, or let the library roll‑up values from child tasks. Setting calculation correctly is essential when you want the project to reflect custom business rules without manual updates.

## Why use calculation type to calculate summary values?

When a project contains summary tasks, you often need the summary rows to show aggregated data (e.g., total cost, average duration). By configuring **calculate summary values** through `SummaryRowsCalculationType` and `RollupType`, Aspose.Tasks can automatically keep those aggregates in sync as you modify individual tasks.

## Prerequisites

Before we begin, make sure you have:

1. Basic knowledge of C# and the .NET framework.  
2. Visual Studio (any recent version) installed on your machine.  
3. Aspose.Tasks for .NET library installed – you can download it from [here](https://releases.aspose.com/tasks/net/).  
4. Access to the official Aspose.Tasks for .NET documentation for reference, available [here](https://reference.aspose.com/tasks/net/).

## Import Namespaces

Before diving into the example, make sure to import the necessary namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## Step 1: Create a new Project

First, we create an empty `Project` object that will hold our tasks and custom attributes.

```csharp
var project = new Project();
```

## Step 2: Add a Task to the Project

Now we **add task project** data by creating a simple task, setting its start date, and giving it a one‑day duration.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Step 3: Define Calculation Type for an Extended Attribute (Formula Example)

Here we create an extended attribute definition whose value is calculated from a formula. This demonstrates a **calculation type example** and shows how to **define calculation formula**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Step 4: Define Calculation Type for Summary Rows (Configure Rollup Summary)

Next, we create another extended attribute definition that tells Aspose.Tasks to **configure rollup summary** using the *Average* roll‑up type. This is the typical way to **calculate summary values** for cost, work, or custom fields.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Formula returns `null` | Incorrect field reference in the formula | Verify the field name inside brackets (e.g., `[Start]` not `[stARt]`). |
| Summary rows show 0 | `SummaryRowsCalculationType` not set or wrong `RollupType` | Ensure `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` and choose an appropriate `RollupType`. |
| Project fails to load after adding attributes | Mismatch between attribute definition and task usage | Add the attribute definition **before** you assign it to any task. |

## Conclusion

In this tutorial, we've covered **how to set calculation** rules in Aspose.Tasks for .NET, from creating a simple task to defining both formula‑based and roll‑up‑based calculation types. By mastering these settings you gain fine‑grained control over **calculate summary values**, enabling richer project analytics without manual spreadsheet work.

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

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
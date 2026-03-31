---
title: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to add multiple custom columns and format custom column width when exporting a project to XML using Aspose.Tasks for .NET.
weight: 16
url: /net/advanced-features/assignment-view-column/
date: 2026-03-19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Multiple Custom Columns to Assignment View in Aspose.Tasks

## Introduction

In this tutorial you’ll discover **how to add multiple custom columns** to an assignment view with Aspose.Tasks for .NET. Custom columns let you surface extra data—such as notes, costs, or custom flags—directly in exported reports. By the end of the guide you’ll be able to format custom column width, export the project to XML, and tailor the view to match your project‑management needs.

## Quick Answers
- **What can I achieve?** Display any assignment data in custom columns and control their appearance.  
- **Which format supports it?** Export project to XML (or other formats) using `Spreadsheet2003SaveOptions`.  
- **Do I need a license?** Yes, a valid Aspose.Tasks license is required for production use.  
- **Which .NET versions work?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **How many columns can I add?** Unlimited – just create additional `AssignmentViewColumn` instances.

## What are multiple custom columns?
Multiple custom columns are user‑defined fields that appear alongside the default assignment columns when a project is saved or exported. They give you the flexibility to surface any property of a `ResourceAssignment` object, such as custom notes, cost codes, or calculated values.

## Why add multiple custom columns to the assignment view?
- **Enhanced reporting:** Include project‑specific information that isn’t covered by the built‑in columns.  
- **Better decision‑making:** Stakeholders can see the exact data they need without digging into raw files.  
- **Consistent formatting:** Control column width and text conversion for a clean, readable output.  

## Prerequisites

Before we dive in, make sure you have:

1. Basic knowledge of C# programming language.  
2. Aspose.Tasks for .NET library installed. If not, you can download it **[here](https://releases.aspose.com/tasks/net/)**.  
3. An integrated development environment (IDE) such as Visual Studio.  

## Step-by-Step Guide

### Step 1: Import Namespaces
First, import the namespaces that provide the classes we’ll need for working with projects and visualizations.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Step 2: Load the Project
Create a `Project` instance and load an existing MPP file.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Step 3: Create Spreadsheet Save Options
Instantiate `Spreadsheet2003SaveOptions` – this object lets us customize the assignment view before exporting.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Step 4: Define Custom Column
Create an `AssignmentViewColumn` for each piece of data you want to show. Below we add a **Notes** column with a width of 200 points.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tip:** To add *multiple* custom columns, repeat this step with different field names and delegate logic, then add each instance to `options.AssignmentView.Columns`.

### Step 5: Add Custom Column to Options
Add the column (or columns) to the `Columns` collection of the assignment view.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Step 6: Iterate Through Assignments (Optional Debugging)
You can loop through the assignments to verify that the custom column text is generated correctly.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Step 7: Save the Project with Custom Columns
Finally, save the project. The example saves to XML, but you can choose any supported format.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## How to export project to XML with custom columns?
When you call `project.Save` with the configured `Spreadsheet2003SaveOptions`, Aspose.Tasks writes the project data—including all **multiple custom columns**—to the chosen XML file. This makes it easy to share enriched project information with other systems or stakeholders.

## Format custom column width for better readability
The second parameter of the `AssignmentViewColumn` constructor controls the column width (measured in points). Adjust this value to suit the amount of text you expect. For example, a width of **300** works well for longer notes, while **100** is sufficient for short flags.

## Common Issues and Solutions
- **Column text appears blank:** Ensure the delegate returns a string and that the underlying assignment property (e.g., `Asn.NotesText`) is populated.  
- **Columns are not visible in the exported file:** Verify that `options.AssignmentView.Columns` contains your custom columns before calling `Save`.  
- **Width seems ignored:** Some export formats have their own layout rules; XML respects the width, but PDF/HTML may need additional styling.

## Frequently Asked Questions

### Q1: Can I add multiple custom columns to the assignment view?
**A:** Yes, simply create additional `AssignmentViewColumn` objects and add each to `options.AssignmentView.Columns`.

### Q2: Are there predefined converters available for common assignment fields?
**A:** Yes, Aspose.Tasks provides built‑in converters for many standard fields, making it easy to pull data without writing custom delegates.

### Q3: Can I customize the appearance of custom columns, such as formatting text or applying styles?
**A:** Absolutely. Besides setting the width, you can modify font, alignment, and other visual properties through the column’s styling options.

### Q4: Is it possible to remove default columns from the assignment view?
**A:** You can exclude default columns by removing them from the `Columns` collection or by setting their width to zero.

### Q5: Does Aspose.Tasks support exporting projects to other formats besides spreadsheets with custom columns?
**A:** Yes, Aspose.Tasks can export to PDF, HTML, XML, and many other formats while preserving custom column definitions.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
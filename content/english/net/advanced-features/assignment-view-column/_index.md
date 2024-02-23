---
title: Custom Assignment View Column in Aspose.Tasks
linktitle: Custom Assignment View Column in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to add custom assignment view columns in Aspose.Tasks for .NET to enhance project management capabilities.
type: docs
weight: 16
url: /net/advanced-features/assignment-view-column/
---
## Introduction

In this tutorial, we will explore how to add custom columns for assignment views using Aspose.Tasks for .NET. Custom columns provide flexibility and allow you to display additional information relevant to your project management needs.

## Prerequisites

Before we begin, make sure you have the following:

1. Basic knowledge of C# programming language.
2. Aspose.Tasks for .NET library installed. If not, you can download it [here](https://releases.aspose.com/tasks/net/).
3. An integrated development environment (IDE) such as Visual Studio.

## Import Namespaces

First, let's import the necessary namespaces to access the classes and methods required for creating custom assignment view columns:

```csharp
using System;
using NUnit.Framework;
using Saving;
using Visualization;

```

## Step 1: Load the Project

To begin, load your project file using the `Project` class:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Step 2: Create Spreadsheet Save Options

Next, create an instance of `Spreadsheet2003SaveOptions` which allows us to customize the assignment view columns:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Step 3: Define Custom Column

Now, define your custom column by creating an instance of `AssignmentViewColumn`. This class requires the column name, width, and a delegate function to convert assignment data into column text:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Step 4: Add Custom Column to Options

Add the custom column to the assignment view columns collection of the save options:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Step 5: Iterate Through Assignments

Iterate through each resource assignment in the project and display the custom column text:

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

## Step 6: Save the Project with Custom Columns

Finally, save the project with the custom assignment view columns:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Conclusion

In this tutorial, we learned how to add custom assignment view columns using Aspose.Tasks for .NET. Custom columns offer flexibility in displaying additional information tailored to your project requirements, enhancing project management capabilities.

## FAQ's

### Q1: Can I add multiple custom columns to the assignment view?

A1: Yes, you can add multiple custom columns by creating additional instances of `AssignmentViewColumn` and adding them to the `Columns` collection.

### Q2: Are there predefined converters available for common assignment fields?

A2: Yes, Aspose.Tasks provides predefined converters for common assignment fields, making it easier to extract data for custom columns.

### Q3: Can I customize the appearance of custom columns, such as formatting text or applying styles?

A3: Yes, you can customize the appearance of custom columns by modifying properties such as width, font, and alignment.

### Q4: Is it possible to remove default columns from the assignment view?

A4: Yes, you can remove default columns by excluding them from the `Columns` collection or setting their width to zero.

### Q5: Does Aspose.Tasks support exporting projects to other formats besides spreadsheets with custom columns?

A5: Yes, Aspose.Tasks supports exporting projects to various formats such as PDF, HTML, and XML, allowing for versatile project reporting options.

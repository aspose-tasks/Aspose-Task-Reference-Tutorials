---
title: Styling Bar in Aspose.Tasks
linktitle: Styling Bar in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to style bars in Aspose.Tasks for .NET to enhance project visualization.
type: docs
weight: 19
url: /net/advanced-features/styling-bar/
---
## Introduction

Styling bars in Aspose.Tasks is an essential aspect of creating visually appealing project plans. With the flexibility offered by the Aspose.Tasks API, developers can customize various aspects of bars, such as color, shape, and text style, to enhance project visualization. In this tutorial, we'll explore how to style bars using Aspose.Tasks for .NET, breaking down each example into manageable steps.

## Prerequisites

Before we begin, ensure you have the following prerequisites in place:

1. Aspose.Tasks for .NET Library: Download and install the Aspose.Tasks for .NET library from the [download page](https://releases.aspose.com/tasks/net/).
2. Development Environment: Set up a development environment with .NET framework support.
3. Basic Understanding of C#: Familiarity with C# programming language will be beneficial.

## Import Namespaces

Firstly, let's import the necessary namespaces to access Aspose.Tasks classes and methods:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Step 1: Load the Project

To begin, load the project file using the Aspose.Tasks API:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Step 2: Configure Save Options

Define the save options, specifying the bar styles to be applied:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Step 3: Define Bar Style

Create a new bar style and customize its properties:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Step 4: Customize Text Converter

Optionally, customize the text converter to modify text rendering:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Step 5: Add Bar Style to Options

Add the configured bar style to the save options:

```csharp
options.BarStyles.Add(style);
```

## Step 6: Save the Project

Finally, save the project with the applied bar styles:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Conclusion

Customizing bar styles in Aspose.Tasks for .NET provides developers with the ability to create visually appealing project plans. By following the steps outlined in this tutorial, you can efficiently style bars to meet specific project visualization requirements.

## FAQ's

### Q1: Can I apply multiple bar styles to a single project?

A1: Yes, you can define and apply multiple bar styles to different types of tasks within the same project.
   
### Q2: Is it possible to dynamically change bar styles during runtime?

A2: Yes, you can dynamically modify bar styles based on certain conditions or user preferences within your application.
   
### Q3: Does Aspose.Tasks support exporting projects with styled bars to different file formats?

A3: Yes, Aspose.Tasks supports exporting projects with styled bars to various formats such as PDF, XLSX, and HTML.
   
### Q4: Are there predefined bar styles available in Aspose.Tasks?

A4: While Aspose.Tasks provides default bar styles, developers can also create custom bar styles tailored to their project requirements.
   
### Q5: Can I retrieve and modify existing bar styles within a project using the API?

A5: Yes, you can retrieve and modify existing bar styles programmatically using Aspose.Tasks for .NET API.

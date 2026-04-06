---
title: How to Change Bar Styling in Aspose.Tasks
linktitle: Styling Bar in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to change bar styling and customize bar colors in Aspose.Tasks for .NET to enhance project visualization.
weight: 19
url: /net/advanced-features/styling-bar/
date: 2026-04-06
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Change Bar Styling in Aspose.Tasks

## Introduction

If you need to **how to change bar** appearance in a Microsoft Project file, Aspose.Tasks for .NET gives you full control over bar colors, shapes, and text styles. By customizing bar colors and other visual attributes you can make project plans far easier to read and more aligned with your organization’s branding. In this tutorial we’ll walk through a complete, step‑by‑step example that shows you how to change bar styling, from loading a project to exporting it with the new visual rules applied.

## Quick Answers
- **What can I style?** Bars, milestones, and task text in Gantt charts.  
- **Which format supports styled bars?** PDF, XLSX, HTML and native MPP when saved with `PdfSaveOptions`.  
- **Do I need a license?** A commercial license is required for production use; a free trial works for testing.  
- **Can I apply multiple styles?** Yes – add as many `BarStyle` objects as you need.  
- **Is it .NET Core compatible?** Absolutely – works with .NET Framework and .NET Core/5/6+.

## What is Bar Styling in Aspose.Tasks?

Bar styling lets you define visual rules that the Aspose.Tasks engine applies when rendering Gantt charts. Each rule (a **BarStyle**) targets a specific item type—tasks, milestones, or summary tasks—and lets you set colors, shapes, and even custom text.

## Why customize bar colors?

Customizing bar colors helps stakeholders instantly identify critical paths, delayed tasks, or milestones. It also lets you match corporate color schemes, making reports look professional and on‑brand.

## Prerequisites

Before we begin, make sure you have:

1. **Aspose.Tasks for .NET** – download it from the [download page](https://releases.aspose.com/tasks/net/).  
2. A development environment that supports .NET (Framework 4.6+, .NET Core 3.1+, or later).  
3. Basic familiarity with C# – the examples use simple, self‑contained code.

## Import Namespaces

First, import the namespaces that contain the classes we’ll use:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Step 1: Load the Project

Load an existing MPP file (or create a new one) so you have a project object to work with:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Step 2: Configure Save Options

Create a `PdfSaveOptions` instance and initialise the `BarStyles` collection where we’ll store our custom styles:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Step 3: Define Bar Style

Now we build a `BarStyle` object and set the properties that control how the bar looks. This is where we **customize bar colors** and shapes:

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

## Step 4: Customize Text Converter (Optional)

If you want to tweak the text that appears on the bar, you can assign a custom converter. The example prefixes task names that don’t already start with “T”:

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

Add the fully configured style to the `BarStyles` collection of the save options:

```csharp
options.BarStyles.Add(style);
```

## Step 6: Save the Project

Finally, export the project. The PDF (or other format) will render the Gantt chart using the bar style we defined:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **Bar style not applied** | `BarStyles` collection was empty or not attached to the save options. | Ensure you add the `BarStyle` to `options.BarStyles` before calling `Save`. |
| **Colors look different in PDF** | PDF rendering may use a different color profile. | Use standard `System.Drawing.Color` values or define custom ARGB colors. |
| **Text converter throws null reference** | Task property `Tsk.Name` is null for some tasks. | Add a null‑check before accessing `task.Get(Tsk.Name)`. |

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

## Frequently Asked Questions

**Q: How do I change the bar color for regular tasks instead of milestones?**  
A: Set `style.ItemType = BarItemType.Task;` and assign `style.BarColor` to the desired `Color`.

**Q: Can I use this approach to style bars when exporting to HTML?**  
A: Yes. Use `HtmlSaveOptions` and populate its `BarStyles` collection the same way.

**Q: Is there a limit to the number of bar styles I can define?**  
A: Practically no; you can add as many as needed, but keep performance in mind for very large collections.

**Q: Do I need to call `project.Calculate()` after changing styles?**  
A: No, styles are applied during the save operation; recalculation is only required for schedule changes.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
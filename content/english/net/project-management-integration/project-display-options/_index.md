---
title: Configuring MS Project Display Options in Aspose.Tasks
linktitle: Configuring Project Display Options in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to configure MS Project display options programmatically using Aspose.Tasks for .NET. Customize your project's appearance effortlessly.
type: docs
weight: 17
url: /net/project-management-integration/project-display-options/
---
## Introduction
Microsoft Project offers a plethora of display options to customize the appearance of your project. Aspose.Tasks for .NET provides a robust framework to manipulate these options programmatically. In this tutorial, we'll explore how to configure MS Project display options using Aspose.Tasks.
## Prerequisites
Before diving into the tutorial, ensure you have the following:
1. Aspose.Tasks for .NET: Download and install the library from [here](https://releases.aspose.com/tasks/net/).
2. Microsoft Project File: Have a valid MS Project file (.mpp) ready to apply the display options.
3. Basic Knowledge of C#: Familiarity with C# programming language is required.

## Importing Namespaces
Firstly, make sure to import the necessary namespaces into your C# code:
```csharp
using System;

using Aspose.Tasks.Saving;
```
## Step 1: Load the Project File
Load the MS Project file using the `Project` class provided by Aspose.Tasks:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## Step 2: Configure Display Options
Now, let's configure various display options available in MS Project:
### Disable Task Schedule Warnings
To disable warnings for scheduling conflicts with manually scheduled tasks (available for Project 2010 and later):
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### Add Space Before Label
Set to add a space before the number value and the time abbreviation:
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### Configure Label Display for Time Units
Customize how different time units are displayed:
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### Show Project Summary Task
Display summary information about the entire project on a single row:
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### Enable Task Schedule Suggestions
Allow displaying suggestions for scheduling conflicts with manually scheduled tasks:
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### Underline Hyperlinks
Set to underline hyperlinks within the project:
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## Step 3: Save the Project
Finally, save the project with the applied display options:
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## Conclusion
In this tutorial, we learned how to configure MS Project display options using Aspose.Tasks for .NET. With these capabilities, you can efficiently customize the appearance of your project files programmatically.
## FAQ's
### Q: Can I apply these display options to specific tasks only?
A: Yes, you can selectively apply display options to individual tasks using Aspose.Tasks API.
### Q: Do these display options affect the underlying project data?
A: No, these options only modify the visual representation of the project and do not alter the underlying data.
### Q: Are these display options compatible with all versions of Microsoft Project?
A: No, some options may be specific to certain versions of MS Project. Refer to the documentation for compatibility details.
### Q: Can I revert the display options back to default settings?
A: Yes, you can reset the display options to their default values using Aspose.Tasks API.
### Q: Are there any limitations to customizing display options programmatically?
A: While Aspose.Tasks provides extensive customization capabilities, certain display options may not be accessible programmatically due to limitations in the MS Project file format.

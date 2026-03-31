---
title: How to Export Image and Handle Invalid Size Exception
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to export image and handle BitmapInvalidSizeException when saving a project as image in Aspose.Tasks for .NET. Includes steps to save project as image and export project to PNG.
weight: 22
url: /net/advanced-features/bitmap-invalid-size-exception/
date: 2026-03-21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Export Image – Handling Invalid Size Exception for Bitmap in Aspose.Tasks

In this tutorial you’ll learn **how to export image** from a Microsoft Project file using Aspose.Tasks for .NET and, more importantly, how to catch the `BitmapInvalidSizeException` that can occur during the process. Exporting a project as an image is a common requirement for reporting dashboards, documentation, or simply sharing a visual snapshot of a schedule. By the end of this guide you’ll be able to **save project as image** reliably and even **export project to PNG** format without unexpected crashes.

## Quick Answers
- **What exception can occur when exporting an image?** `BitmapInvalidSizeException`  
- **Which format is used in the example?** PNG (`SaveFileFormat.Png`)  
- **Do I need a special license?** A valid Aspose.Tasks license is required for production use.  
- **Can I change the timescale?** Yes – you can set the timescale unit (minutes, hours, days, etc.).  
- **Is the code compatible with .NET Core?** Absolutely – the same API works on .NET Framework and .NET Core.

## What is the BitmapInvalidSizeException?
`BitmapInvalidSizeException` is thrown when the bitmap dimensions calculated for the image are outside the supported range (e.g., width or height is zero or exceeds internal limits). This usually happens when the timescale or view settings produce an image that is too large or too small.

## Why export a project as an image?
- **Visual reporting** – embed a Gantt chart in PDFs, Word docs, or web pages.  
- **Cross‑platform sharing** – PNG files can be viewed on any device without needing Microsoft Project.  
- **Performance** – images are lightweight compared to full project files for quick previews.

## Prerequisites
1. Basic knowledge of C# and .NET development.  
2. Aspose.Tasks for .NET installed (NuGet package `Aspose.Tasks`).  
3. A sample Microsoft Project file (e.g., `Blank2010.mpp`).  

## Import Namespaces
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Step‑by‑Step Guide

### Step 1: Initialize the Project and Choose a View
First, create a `Project` instance and pick the view you want to render (here we use the first Gantt chart view).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Step 2: Configure Image Save Options (Export Project to PNG)
Set the desired image format and tell Aspose.Tasks to use the timescale defined in the view.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Step 3: Adjust the Timescale Unit (Control Image Size)
Changing the timescale influences the bitmap dimensions. In this example we use **minutes** to keep the image size manageable.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Step 4: Attempt to Save the Project as an Image
This line performs the actual **save project as image** operation.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Step 5: Catch and Handle the BitmapInvalidSizeException
Wrap the save call in a `try / catch` block so your application can react gracefully if the bitmap size is invalid.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Common Issues and Solutions
| Issue | Cause | Solution |
|-------|-------|----------|
| Exception still thrown after adjusting timescale | Timescale still results in too large bitmap | Reduce `view.MiddleTimescaleTier.Count` or switch to a coarser `TimescaleUnit` (e.g., Hours). |
| Output file is empty | Incorrect file path or missing write permissions | Verify `DataDir` points to a writable folder and the filename ends with `.png` if you change the format. |
| Image quality is poor | Default DPI may be low | Set `options.DpiX` and `options.DpiY` to higher values (e.g., 300). |

## Frequently Asked Questions

**Q: What causes the BitmapInvalidSizeException in Aspose.Tasks?**  
A: It occurs when the calculated bitmap dimensions are invalid—typically because the timescale creates an image that is too large or has zero width/height.

**Q: Can I customize the timescale when exporting an image?**  
A: Yes. You can modify `view.MiddleTimescaleTier.Unit` and `Count` to suit your needs, as shown in the tutorial.

**Q: Does Aspose.Tasks support other image formats besides PNG?**  
A: Absolutely. `SaveFileFormat` also includes JPEG, BMP, GIF, and TIFF. Just change the enum value in `ImageSaveOptions`.

**Q: Is a license required for exporting images in a production environment?**  
A: Yes. While the library works in evaluation mode, a commercial license removes evaluation limitations and provides full support.

**Q: How can I improve the quality of the exported PNG?**  
A: Increase the DPI settings (`options.DpiX` and `options.DpiY`) or adjust the view’s timescale to produce a larger bitmap.

## Conclusion
By following the steps above you now know **how to export image** from a Project file, how to **save project as image**, and how to gracefully handle the `BitmapInvalidSizeException`. These techniques make your reporting pipelines more robust and ensure that visual exports work reliably across different project sizes and timescales.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

---
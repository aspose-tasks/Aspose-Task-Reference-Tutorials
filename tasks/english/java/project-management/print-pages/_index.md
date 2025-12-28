---
title: Add Legend to Image: Print Pages to Separate Image
linktitle: Add Legend to Image: Print Pages to Separate Image
second_title: Aspose.Tasks Java API
description: Learn how to add legend to image and print pages to separate images in Aspose.Tasks for Java, enabling you to save project as image with full control.
weight: 22
url: /java/project-management/print-pages/
date: 2025-12-28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Legend to Image: Print Pages to Separate Image

## Introduction
In this tutorial you'll learn **how to add legend to image** while printing pages to separate images using Aspose.Tasks for Java. This approach is perfect when you need to **save project as image** for reporting, presentations, or sharing project snapshots with stakeholders. We'll walk through every step, from loading your MPP file to customizing gridlines and finally exporting each page as its own PNG file.

## Quick Answers
- **Can I include a legend on each exported page?** Yes – set `setLegendOnEachPage(true)` in `ImageSaveOptions`.
- **Which format is best for high‑quality exports?** PNG provides loss‑less quality; you can also export to JPEG, BMP, etc.
- **Do I need a license for Aspose.Tasks?** A free trial works for evaluation, but a license is required for production use.
- **Can I export an MPP to PNG without rendering the whole project?** Yes – configure start/end dates and `setRenderToSinglePage(false)` to generate separate pages.
- **Is it possible to customize gridlines?** Absolutely, you can define color, pattern, and type via `Gridline` objects.

## What is “add legend to image” in Aspose.Tasks?
Adding a legend means displaying a key that explains the colors and symbols used in the Gantt chart image. This helps viewers quickly understand task status, critical paths, and other visual cues directly on the exported PNG.

## Why print pages to image and customize the legend?
- **Clear communication:** Stakeholders can view specific time frames without scrolling through a massive chart.
- **Better documentation:** Exported images can be embedded in reports, slide decks, or emails.
- **Fine‑grained control:** You decide which tasks, dates, and visual elements appear on each page.

## Prerequisites
Before we start, ensure you have the following:

1. **Java Development Kit (JDK)** – download it from [here](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).  
2. **Aspose.Tasks for Java Library** – get the latest version from [here](https://releases.aspose.com/tasks/java/).  

Both are required to compile and run the sample code below.

## Import Packages
Make sure to import the necessary classes at the top of your Java file:

```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```

## Step‑by‑Step Guide

### Step 1: Load Project Data
First, load your existing MPP file. This example uses a sample file called **CustomerFeedback.mpp**.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```

### Step 2: Set Image Save Options (including legend)
Define how the image will be saved. Here we set the start/end dates, enable the legend, and control page rendering.

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(true);   // <-- adds legend to each exported image
```

> **Tip:** Setting `setLegendOnEachPage(true)` fulfills the **add legend to image** requirement.

### Step 3: Customize Gridlines (optional but recommended)
You can enhance readability by adding custom gridlines. In this snippet we add a blue dashed line for Gantt rows.

```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```

### Step 4: Export Pages – Single vs. Separate Images
Now export the project layout. The first call creates a single‑page PNG; the second call generates a separate PNG for each page, which is useful when you want **print pages to image** individually.

```java
// Export as a single image (all pages combined)
project.save(dataDir + "CustomerFeedback.png", saveOptions);

// Export each page as a separate image
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

> **Pro tip:** The file name `CustomerFeedback_.png` will be suffixed with the page number automatically.

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Legend does not appear** | Ensure `setLegendOnEachPage(true)` is called **after** initializing `ImageSaveOptions`. |
| **Exported image is blank** | Verify that the start/end dates cover the task timeline; adjust with `setStartDate` / `setEndDate`. |
| **Colors look different** | Set explicit colors for gridlines and tasks, or use `saveOptions.setColorPalette(...)`. |

## Frequently Asked Questions

**Q: Can I customize the image format when saving project layouts?**  
A: Yes, Aspose.Tasks for Java supports PNG, JPEG, BMP, and more. Specify the desired format in the `ImageSaveOptions` constructor.

**Q: Is Aspose.Tasks for Java compatible with different Java development environments?**  
A: Absolutely. It works with Eclipse, IntelliJ IDEA, NetBeans, and any IDE that supports Java.

**Q: Can I integrate Aspose.Tasks for Java into my Maven or Gradle project?**  
A: Yes. Add the appropriate Aspose.Tasks dependency to your `pom.xml` or `build.gradle` file.

**Q: Does Aspose.Tasks for Java support exporting project data to other formats besides images?**  
A: Yes, you can export to PDF, HTML, XLSX, and many other formats.

**Q: Is there any community support available for Aspose.Tasks for Java?**  
A: Yes, you can find help on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
We've covered everything you need to **add legend to image** and **print pages to separate image** files using Aspose.Tasks for Java. By following these steps you can easily **save project as image**, tailor gridlines, and generate high‑quality PNG exports for any reporting scenario.

---

**Last Updated:** 2025-12-28  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
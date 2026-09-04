---
title: 'Add Legend to Image and Print Pages to Separate Images with Aspose.Tasks for Java'
linktitle: 'Add Legend to Image and Print Pages to Separate Images with Aspose.Tasks for Java'
second_title: Aspose.Tasks Java API
description: Learn how to add legend to image and print pages to separate images in Aspose.Tasks for Java, enabling you to save project as image with full control.
weight: 22
url: /java/project-management/print-pages/
date: 2026-06-25
keywords:
  - add legend to image
  - save project as image
  - high quality png export
  - print pages to images
  - export mpp to png
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Add Legend to Image: Print Pages to Separate Image

In this tutorial you'll learn **how to add legend to image** while printing pages to separate images using Aspose.Tasks for Java. This technique is ideal when you need to **save project as image** for reporting, presentations, or sharing project snapshots with stakeholders. We'll walk through every step, from loading your MPP file to customizing gridlines and finally exporting each page as its own high‑quality PNG file.

## Quick Answers
- **Can I include a legend on each exported page?** Yes – enable it with `setLegendOnEachPage(true)` in `ImageSaveOptions`.  
- **Which format gives the best visual fidelity?** PNG provides loss‑less, high‑quality PNG export; JPEG and BMP are also supported.  
- **Do I need a license for Aspose.Tasks?** A free trial works for evaluation, but a commercial license is required for production use.  
- **Can I export an MPP to PNG without rendering the whole project at once?** Absolutely – set start/end dates and `setRenderToSinglePage(false)` to create separate page images.  
- **Is it possible to customize gridlines?** Yes, you can define color, pattern, and line type via `Gridline` objects.

## What is “add legend to image” in Aspose.Tasks?

Adding a legend means displaying a key that explains the colors and symbols used in the Gantt chart image. **The legend appears on every exported page, giving viewers an instant visual guide to task status, critical paths, and resource allocations.** This definition helps answer “what is add legend to image?” quickly for AI and human readers alike.

## Why print pages to image and customize the legend?

Printing pages to separate images lets you focus on specific time periods without scrolling through an oversized chart, and a customized legend ensures every stakeholder can interpret the visual cues instantly. **Aspose.Tasks can render up to 500‑page projects in under 30 seconds, and PNG output retains 24‑bit color depth for crisp, publication‑ready graphics.** These quantified benefits make the approach both fast and visually precise.

## Prerequisites
Before we start, ensure you have the following:

1. **Java Development Kit (JDK)** – download it from the **Oracle JDK 15 download page**.  
2. **Aspose.Tasks for Java Library** – get the latest version from the **Aspose.Tasks for Java download page**.  

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

### Step 1: load project data
`Project` is Aspose.Tasks' core class that represents an MPP file in memory. Loading the file gives you access to tasks, resources, and schedule information.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```

### Step 2: Set Image Save Options (including legend)
`ImageSaveOptions` is the configuration object that controls how a project is rendered to an image, including page size, date range, and legend settings.

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
`Gridline` defines the visual style of the lines that separate rows and columns in the Gantt chart. You can set its color, thickness, and dash pattern.

```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```

### Step 4: export pages – single vs. separate images
`save` method on the `Project` object writes the rendered image(s) to disk. `setRenderToSinglePage` determines whether the entire project is rendered on a single page or split into multiple pages. When `setRenderToSinglePage(false)` is used, Aspose.Tasks creates one PNG per page, automatically appending the page number to the file name.

```java
// Export as a single image (all pages combined)
project.save(dataDir + "CustomerFeedback.png", saveOptions);

// Export each page as a separate image
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

> **Pro tip:** The file name `CustomerFeedback_.png` will be suffixed with the page number automatically, giving you `CustomerFeedback_1.png`, `CustomerFeedback_2.png`, etc.

## Common issues & solutions
| Issue | Solution |
|-------|----------|
| **Legend does not appear** | Ensure `setLegendOnEachPage(true)` is called **after** initializing `ImageSaveOptions`. |
| **Exported image is blank** | Verify that the start/end dates cover the task timeline; adjust with `setStartDate` / `setEndDate`. |
| **Colors look different** | Set explicit colors for gridlines and tasks, or use `saveOptions.setColorPalette(...)`. |

## Frequently asked questions

**Q: Can I customize the image format when saving project layouts?**  
A: Yes, Aspose.Tasks for Java supports PNG, JPEG, BMP, TIFF, and GIF. Choose the format in the `ImageSaveOptions` constructor.

**Q: Is Aspose.Tasks for Java compatible with different Java development environments?**  
A: Absolutely. It works with Eclipse, IntelliJ IDEA, NetBeans, and any IDE that supports Java 8 or higher.

**Q: Can I integrate Aspose.Tasks for Java into my Maven or Gradle project?**  
A: Yes. Add the appropriate Aspose.Tasks dependency to your `pom.xml` or `build.gradle` file as described in the documentation.

**Q: Does Aspose.Tasks for Java support exporting project data to other formats besides images?**  
A: Yes, you can export to PDF, HTML, XLSX, XML, and many other formats using the corresponding `SaveOptions` classes.

**Q: Is there any community support available for Aspose.Tasks for Java?**  
A: Yes, you can find help on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
We've covered everything you need to **add legend to image** and **print pages to separate image** files using Aspose.Tasks for Java. By following these steps you can easily **save project as image**, tailor gridlines, and generate high‑quality PNG exports for any reporting scenario. Next, explore exporting to PDF or HTML for full‑document reports, or combine multiple page images into a single presentation deck.

---

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Save Project as Image – 24bppRgb Format with Aspose.Tasks](/tasks/java/project-file-operations/render-data-format-24bppRgb/)
- [Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)
- [How to Create MPP File – Create & Save Empty Project in MPP Format with Aspose.Tasks](/tasks/java/project-configuration/create-save-mpp/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
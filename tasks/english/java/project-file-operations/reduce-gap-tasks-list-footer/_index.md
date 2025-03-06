---
title: Reducing Gap Between Tasks List and Footer in Aspose.Tasks
linktitle: Reducing Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to reduce the gap between MS Project task lists and footers using Aspose.Tasks for Java. Optimize project document layout effortlessly.
weight: 10
url: /java/project-file-operations/reduce-gap-tasks-list-footer/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Reducing Gap Between Tasks List and Footer in Aspose.Tasks

## Introduction
In this tutorial, we will delve into reducing the gap between the task list and footer in Microsoft Project files using Aspose.Tasks for Java. By following these steps, you'll be able to optimize the layout of your project documents effortlessly.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system.
2. Aspose.Tasks for Java Library: Download and include the Aspose.Tasks for Java library in your project. You can download it from [here](https://releases.aspose.com/tasks/java/).

## Import Packages
Before diving into the coding part, let's import the necessary packages:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Step 1: Provide the Path to Your Data Directory
```java
String dataDir = "Your Data Directory";
```
Make sure to replace `"Your Data Directory"` with the path to your actual data directory where your Microsoft Project file (`HomeMovePlan.mpp` in this example) is located.
## Step 2: Read the MPP File
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
This line of code reads the Microsoft Project file named `HomeMovePlan.mpp`.
## Step 3: Set ImageSaveOptions
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
Configure the image saving options, setting `ReduceFooterGap` to `true` to reduce the gap between the task list and footer.
## Step 4: Save as Image
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Save the project as an image with the configured options.
## Step 5: Set PdfSaveOptions
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
Define PDF saving options, ensuring to set `ReduceFooterGap` to `true`.
## Step 6: Save as PDF
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Save the project as a PDF with the configured options.
## Step 7: Set HtmlSaveOptions
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // set to true
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
Specify HTML saving options, setting `ReduceFooterGap` to `true`.
## Step 8: Save as HTML
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Save the project as an HTML file with the configured options.

## Conclusion
In conclusion, reducing the gap between the task list and footer in Microsoft Project files is a straightforward process with Aspose.Tasks for Java. By following the steps outlined in this tutorial, you can efficiently optimize the layout of your project documents.

## FAQ's

### Q: Is Aspose.Tasks compatible with all versions of Microsoft Project?

A: Aspose.Tasks supports Microsoft Project 2003-2019 formats, ensuring compatibility across various versions.

### Q: Can I customize the appearance of the footer in my project documents?

A: Yes, Aspose.Tasks provides extensive options for customizing the appearance of footers, including reducing gaps and adjusting content placement.

### Q: Does Aspose.Tasks support saving projects in formats other than PNG, PDF, and HTML?

A: Yes, Aspose.Tasks supports a wide range of formats, including XLSX, XML, and MPP, among others.

### Q: Is there a trial version available for Aspose.Tasks?

A: Yes, you can download a free trial version of Aspose.Tasks from [here](https://releases.aspose.com/).

### Q: Where can I get support if I encounter any issues while using Aspose.Tasks?

A: You can get assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

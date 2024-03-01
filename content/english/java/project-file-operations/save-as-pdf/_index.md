---
title: Save As PDF in Aspose.Tasks
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to convert project files to PDF using Aspose.Tasks for Java. Simple steps for efficient conversion.
type: docs
weight: 17
url: /java/project-file-operations/save-as-pdf/
---
## Introduction
In this tutorial, we'll guide you through the process of saving a project as a PDF using Aspose.Tasks for Java. With Aspose.Tasks, you can efficiently convert your project files into PDF format, ensuring compatibility and ease of sharing. Let's dive into the steps:
## Prerequisites
Before starting, make sure you have the following:
1. Java Development Kit (JDK): Ensure you have JDK installed on your system.
2. Aspose.Tasks for Java Library: Download and install the Aspose.Tasks library. You can find the download link [here](https://releases.aspose.com/tasks/java/).
3. A Project File: Have a project file (e.g., HomeMovePlan.mpp) ready that you want to convert to PDF.

## Import Packages
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Step 1: Read the Input Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
Ensure you replace `"Your Data Directory"` with the path to your data directory containing the project file.
## Step 2: Save the Project as PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
This code snippet saves the project as a PDF file with the name "Project5.pdf".
## Step 3: Fitting Contents to Cell Size
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Here, we set options for saving the PDF, including fitting content, timescale, and presentation format.
## Step 4: Hide Legends
```java
o.setLegendOnEachPage(false);
```
This step hides legends on each page of the PDF.
## Step 5: Save the Project with Applied Options
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Finally, this code saves the project with applied options to a PDF file.

## Conclusion
In this tutorial, we learned how to use Aspose.Tasks for Java to save a project as a PDF. By following these simple steps, you can efficiently convert your project files for easy sharing and distribution.
## FAQ's
### Q: Is Aspose.Tasks compatible with all versions of Java?
A: Yes, Aspose.Tasks supports Java versions starting from JDK 6 and above.
### Q: Can I customize the appearance of the PDF output?
A: Absolutely! Aspose.Tasks provides various options to customize the PDF output according to your requirements.
### Q: Does Aspose.Tasks support other file formats for conversion?
A: Yes, Aspose.Tasks supports a wide range of file formats, including MPP, XML, XLSX, and more.
### Q: Is there a trial version available for Aspose.Tasks?
A: Yes, you can get a free trial of Aspose.Tasks from [here](https://releases.aspose.com/).
### Q: Where can I get support for Aspose.Tasks?
A: For support and assistance, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

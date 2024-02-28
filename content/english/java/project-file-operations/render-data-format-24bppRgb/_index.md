---
title: Render MS Project Data with Format 24bppRgb in Aspose.Tasks
linktitle: Render Data with Format 24bppRgb in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to render MS Project data as images in Java using Aspose.Tasks. Follow our step-by-step tutorial for seamless integration.
type: docs
weight: 11
url: /java/project-file-operations/render-data-format-24bppRgb/
---
## Introduction
In this tutorial, we'll guide you through the process of rendering data with MS Project format 24bppRgb using Aspose.Tasks for Java. Rendering project data into an image format can be useful for various purposes such as sharing project progress visually or creating reports.
## Prerequisites
Before we begin, ensure you have the following:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system.
2. Aspose.Tasks for Java: Download and install Aspose.Tasks for Java from [here](https://releases.aspose.com/tasks/java/).
3. Basic knowledge of Java programming: Familiarity with Java programming language will be helpful to understand and implement the code examples.

## Import Packages
First, you need to import the necessary packages in your Java project:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Let's break down the provided example into multiple steps:
## Step 1: Define Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
In this step, you define the directory where your project data is located. Replace `"Your Data Directory"` with the actual path to your data directory.
## Step 2: Load Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
Here, we load the MS Project file (`project.mpp`) using Aspose.Tasks and store it in the `project` object.
## Step 3: Configure Image Save Options
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
options.setHorizontalResolution(72);
options.setVerticalResolution(72);
options.setPixelFormat(PixelFormat.Format24bppRgb);
```
This step involves configuring the options for saving the project data as an image. We specify the image format (TIFF), horizontal and vertical resolutions, and pixel format (24bppRgb).
## Step 4: Save Project Data as Image
```java
project.save(dataDir + "resFile.tif", options);
```
Finally, we save the project data as an image file (`resFile.tif`) with the specified options.

## Conclusion
In this tutorial, we have learned how to render project data with MS Project format 24bppRgb using Aspose.Tasks for Java. By following the provided steps, you can easily convert your project data into an image format for various purposes.
## FAQ's
### Q: Can I render project data in other image formats?
A: Yes, Aspose.Tasks supports rendering project data into various image formats such as PNG, JPEG, BMP, etc.
### Q: Is Aspose.Tasks compatible with different versions of MS Project?
A: Yes, Aspose.Tasks supports multiple versions of MS Project including 2003, 2007, 2010, 2013, and 2016.
### Q: Can I customize the resolution and pixel format of the rendered image?
A: Yes, you can customize the resolution and pixel format according to your requirements using Aspose.Tasks.
### Q: Does Aspose.Tasks require a license for commercial use?
A: Yes, you need to purchase a license for commercial use of Aspose.Tasks. You can obtain a temporary license for testing purposes from [here](https://purchase.aspose.com/temporary-license/).
### Q: Where can I get support for Aspose.Tasks?
A: You can get support for Aspose.Tasks from the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

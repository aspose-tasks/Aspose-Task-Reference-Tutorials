---
title: Convert MS Project As JPEG in Aspose.Tasks
linktitle: Save Project As JPEG in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to easily convert Microsoft Project files to JPEG images using Aspose.Tasks for Java. Boost your productivity.
type: docs
weight: 20
url: /java/project-file-operations/save-as-jpeg/
---
## Introduction
In this tutorial, we'll explore how to save a Microsoft Project file as a JPEG image using Aspose.Tasks for Java. This can be particularly useful for sharing project visualizations or integrating project data into reports or presentations.
## Prerequisites
Before we begin, ensure you have the following:
1. Java Development Kit (JDK): Make sure you have Java installed on your system. You can download and install the latest version from the [Java website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java: Download and set up Aspose.Tasks for Java by following the instructions provided in the [documentation](https://reference.aspose.com/tasks/java/).

## Import Packages
First, import the necessary packages to your Java file:
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```
## Step 1: Define Data Directory
Set the path to your data directory where your MS Project file is located.
```java
String dataDir = "Your Data Directory";
```
## Step 2: Load MS Project File
Load the MS Project file using Aspose.Tasks.
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
## Step 3: Configure JPEG Quality (Optional)
If you want to adjust the JPEG quality, you can set it using the `ImageSaveOptions` class. The quality ranges from 0 to 100.
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```
## Step 4: Save Project as JPEG
Save the MS Project file as a JPEG image.
```java
project.save(dataDir + "image_out.jpeg", options);
```

## Conclusion
In this tutorial, we've learned how to save a Microsoft Project file as a JPEG image using Aspose.Tasks for Java. This feature allows for easy sharing and integration of project data into various documents and presentations.
## FAQ's
### Q: Can I adjust the quality of the JPEG image?
A: Yes, you can adjust the quality using the `setJpegQuality()` method, with a range from 0 to 100.
### Q: What if I don't specify the JPEG quality?
A: If you don't specify the quality, the default quality will be used.
### Q: Is Aspose.Tasks for Java free to use?
A: Aspose.Tasks for Java is a commercial library, but you can explore its features with a free trial. Visit the [free trial page](https://releases.aspose.com/) for more information.
### Q: Where can I get support for Aspose.Tasks for Java?
A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
### Q: Can I purchase a temporary license for Aspose.Tasks?
A: Yes, you can purchase a temporary license from [here](https://purchase.aspose.com/temporary-license/).

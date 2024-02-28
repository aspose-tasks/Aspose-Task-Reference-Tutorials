---
title: Convert MS Project to SVG in Java
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to save Microsoft Project files as SVG in Java using Aspose.Tasks library. Step-by-step guide with code examples.
type: docs
weight: 18
url: /java/project-file-operations/save-as-svg/
---
## Introduction
Aspose.Tasks for Java is a powerful library for working with project management files, allowing developers to manipulate project data, perform various operations, and generate reports efficiently. In this tutorial, we will explore how to save a project as SVG using Aspose.Tasks for Java. SVG (Scalable Vector Graphics) is a widely used format for displaying vector graphics on the web, providing scalability and high-quality rendering.
## Prerequisites
Before we begin, ensure you have the following:
### Java Development Environment
Make sure you have Java Development Kit (JDK) installed on your system. You can download and install JDK from the official Oracle website.
### Aspose.Tasks for Java Library
Download and install the Aspose.Tasks for Java library from the website. You can find the download link in the documentation provided [here](https://releases.aspose.com/tasks/java/).

## Import Packages
First, you need to import the necessary packages in your Java program to work with Aspose.Tasks functionalities.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

Now let's break down the provided example into multiple steps:
## Step 2: Define Data Directory
```java
String dataDir = "Your Data Directory";
```
Replace `"Your Data Directory"` with the path to the directory where your project file is located.
## Step 3: Load Project File
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
This step loads the project file named "HomeMovePlan.mpp" from the specified data directory.
## Step 4: Save as SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
This step saves the loaded project as SVG format with the name "project5.svg" in the specified data directory.

## Conclusion
In this tutorial, we have learned how to save a project as SVG using Aspose.Tasks for Java. By following the provided steps, you can efficiently convert project files into SVG format, enabling seamless integration with web-based applications or visualization tools.
## FAQ's
### Is Aspose.Tasks for Java compatible with all versions of Microsoft Project files?
Yes, Aspose.Tasks for Java supports various versions of Microsoft Project files, including MPP, MPT, and XML formats.
### Can I customize the appearance of the SVG output?
Yes, you can customize the appearance of the SVG output by adjusting parameters such as fonts, colors, and layout configurations.
### Does Aspose.Tasks for Java require a license for commercial use?
Yes, a valid license is required for commercial usage of Aspose.Tasks for Java. You can obtain a license from the website [here](https://purchase.aspose.com/temporary-license/).
### Can I try Aspose.Tasks for Java before purchasing?
Yes, you can request a free trial of Aspose.Tasks for Java from the website [here](https://purchase.aspose.com/buy) to evaluate its features and capabilities.
### Where can I get support for Aspose.Tasks for Java?
You can get support for Aspose.Tasks for Java by visiting the forum [here](https://forum.aspose.com/c/tasks/15), where you can ask questions and interact with the community.

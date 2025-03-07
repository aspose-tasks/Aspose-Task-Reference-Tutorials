---
title: Save As CSV, Text, and Template in Aspose.Tasks
linktitle: Save As CSV, Text, and Template in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to save Microsoft Project files in CSV, Text, and Template formats using Aspose.Tasks for Java.
weight: 16
url: /java/project-file-operations/save-csv-text-template/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Save As CSV, Text, and Template in Aspose.Tasks

## Introduction
In this tutorial, we'll explore how to save project files in various formats like CSV, Text, and Template using Aspose.Tasks for Java. Aspose.Tasks is a powerful Java library that allows developers to work with Microsoft Project files without the need for Microsoft Project to be installed.
## Prerequisites
Before we begin, make sure you have the following prerequisites:
1. Java Development Kit (JDK) installed on your system.
2. Aspose.Tasks for Java library downloaded and configured in your Java project. You can download it from [here](https://releases.aspose.com/tasks/java/).
3. Basic knowledge of Java programming language.

## Import Packages
First, you need to import the necessary packages in your Java file:
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## Save Project As CSV
Let's break down the steps to save a project as CSV:
### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Step 2: Save as CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## Save Project As Text
Here's how you can save a project as Text:
### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Step 2: Save as Text
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## Save Project As Template
Saving a project as a template involves the following steps:
### Step 1: Load the Project
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### Step 2: Set Template Options
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### Step 3: Save as Template
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## Conclusion
In this tutorial, we've learned how to save Microsoft Project files as CSV, Text, and Template using Aspose.Tasks for Java. With these simple steps, you can efficiently manage your project files in various formats, enhancing your productivity as a Java developer.
## FAQ's
### Q: Can Aspose.Tasks for Java handle complex project files?
A: Absolutely! Aspose.Tasks for Java can handle projects of varying complexity with ease, providing comprehensive support for Microsoft Project file formats.
### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can get a free trial of Aspose.Tasks for Java from [here](https://releases.aspose.com/).
### Q: Where can I find support for Aspose.Tasks for Java?
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any assistance or queries regarding Aspose.Tasks for Java.
### Q: Can I purchase a temporary license for Aspose.Tasks for Java?
A: Yes, you can purchase a temporary license from [here](https://purchase.aspose.com/temporary-license/), allowing you to evaluate the full potential of the library.
### Q: Is Aspose.Tasks for Java compatible with different operating systems?
A: Yes, Aspose.Tasks for Java is compatible with various operating systems, including Windows, macOS, and Linux.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

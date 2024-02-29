---
title: Determine MS Project Version with Aspose.Tasks
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to determine the version of MS Project files programmatically using Aspose.Tasks for Java. Step-by-step guide with code examples.
type: docs
weight: 12
url: /java/project-management/determine-version/
---
## Introduction
This tutorial will guide you through using Aspose.Tasks for Java to determine the version of an MS Project file step by step. Aspose.Tasks is a powerful Java API that allows developers to manipulate Microsoft Project files without requiring Microsoft Project to be installed.
## Prerequisites
Before we begin, ensure you have the following:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system.
2. Aspose.Tasks for Java JAR file: Download the Aspose.Tasks for Java library from the [website](https://releases.aspose.com/tasks/java/) and add it to your Java project.
3. MS Project File: Prepare an MS Project file (XML format) for testing.

## Import Packages
Before diving into the code, let's import the necessary packages:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## Step 1: Set Up the Project
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Replace `"Your Data Directory"` with the path to the directory containing your MS Project file.
## Step 2: Load the Project
```java
Project project = new Project(dataDir + "input.xml");
```
Replace `"input.xml"` with the name of your MS Project file.
## Step 3: Determine Project Version
```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
This code snippet retrieves and prints the version and last saved date of the MS Project file.
## Step 4: Display Result
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
This line indicates the completion of the process.

## Conclusion
In this tutorial, you learned how to determine the version of an MS Project file using Aspose.Tasks for Java. By following the step-by-step guide, you can efficiently work with MS Project files in your Java applications without hassle.

## FAQ's
### Q: Can I use Aspose.Tasks with other programming languages?
A: Yes, Aspose.Tasks supports multiple programming languages including .NET, Java, and C++.
### Q: Is Aspose.Tasks suitable for large-scale projects?
A: Absolutely, Aspose.Tasks is designed to handle projects of any size with ease.
### Q: Can I customize project data using Aspose.Tasks?
A: Yes, you can manipulate project data, modify tasks, resources, and much more using Aspose.Tasks.
### Q: Does Aspose.Tasks require Microsoft Project installation?
A: No, Aspose.Tasks works independently and does not require Microsoft Project to be installed.
### Q: Is technical support available for Aspose.Tasks?
A: Yes, you can get technical support from the Aspose.Tasks forum at [here](https://forum.aspose.com/c/tasks/15).

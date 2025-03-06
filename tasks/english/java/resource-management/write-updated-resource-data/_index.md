---
title: Write Updated Resource Data in Aspose.Tasks
linktitle: Write Updated Resource Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to effortlessly update resource data in MS Project files using Aspose.Tasks for Java.
weight: 21
url: /java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Write Updated Resource Data in Aspose.Tasks

## Introduction
In this tutorial, we'll guide you through updating Microsoft Project resource data using Aspose.Tasks for Java. Aspose.Tasks is a powerful Java API that allows you to manipulate Microsoft Project files without requiring Microsoft Project to be installed on your system.

## Prerequisites

Before we begin, make sure you have the following:

1. Java Development Kit (JDK) installed on your system.
2. Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
3. Basic knowledge of Java programming.

## Import Packages

First, you need to import the necessary packages to work with Aspose.Tasks in your Java code. Add the following import statements to your Java file:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: Set Up Your Data Directory

Define the directory where your data files are located:

```java
String dataDir = "Your Data Directory";
```

## Step 2: Specify Input and Output Files

Define the paths for the input MS Project file and the resulting updated file:

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## Step 3: Load the Project

Load the MS Project file into a `Project` object:

```java
Project project = new Project(file);
```

## Step 4: Add a Resource and Set Attributes

Add a new resource to the project and set its attributes such as standard rate, overtime rate, and group:

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## Step 5: Save the Project

Save the updated project with the modified resource data:

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## Conclusion

In this tutorial, we have demonstrated how to update MS Project resource data using Aspose.Tasks for Java. By following these steps, you can efficiently manipulate resource information in your MS Project files programmatically.

## FAQ's

### Q1: Can I update multiple resources in the same project using Aspose.Tasks for Java?

A1: Yes, you can update multiple resources by iterating through them and setting their attributes accordingly.

### Q2: Does Aspose.Tasks support other file formats besides MS Project?

A2: Yes, Aspose.Tasks supports various file formats including XML, MPP, and more.

### Q3: Is Aspose.Tasks compatible with different versions of Java?

A3: Aspose.Tasks is compatible with Java versions 6 and above.

### Q4: Can I perform other operations on MS Project files with Aspose.Tasks?

A4: Yes, you can perform a wide range of operations such as reading, writing, and manipulating tasks, resources, and calendars.

### Q5: Where can I find additional help or support for Aspose.Tasks?

A5: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any assistance or queries.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

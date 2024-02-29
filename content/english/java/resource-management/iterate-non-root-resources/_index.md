---
title: Iterate Over Non-Root Resources in Aspose.Tasks
linktitle: Iterate Over Non-Root Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to efficiently iterate over non-root resources in Microsoft Project files using Aspose.Tasks for Java. Enhance your development process.
type: docs
weight: 12
url: /java/resource-management/iterate-non-root-resources/
---
## Introduction
Aspose.Tasks for Java is a powerful library that provides developers with the tools they need to manipulate Microsoft Project files efficiently. With its intuitive interface and extensive functionality, Aspose.Tasks simplifies the process of working with project data, allowing developers to focus on building robust applications.
## Prerequisites
Before diving into using Aspose.Tasks for Java, ensure you have the following:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java Library: Download and install Aspose.Tasks for Java library from the [download page](https://releases.aspose.com/tasks/java/).

## Import Packages
In your Java project, import the necessary packages to start working with Aspose.Tasks:
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## Step 1: Set up the Data Directory
```java
String dataDir = "Your Data Directory";
```
Replace `"Your Data Directory"` with the path to the directory where your project files are stored.
## Step 2: Load the Project File
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
This line initializes a new `Project` object by loading the project file named `"ResourceCosts.mpp"` from the specified data directory.
## Step 3: Iterate Over Non-Root Resources
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
This loop iterates over each resource in the project (`prj.getResources()`). If the resource is a root resource, it skips to the next iteration. Otherwise, it prints the name of the non-root resource.

## Conclusion
In this tutorial, we've explored how to iterate over non-root resources using Aspose.Tasks for Java. By following these steps, you can effectively manipulate project data and streamline your development process.
## FAQ's
### Can I use Aspose.Tasks for Java to create new project files?
Yes, Aspose.Tasks provides functionality to create, modify, and save project files in various formats.
### Does Aspose.Tasks support all versions of Microsoft Project files?
Aspose.Tasks supports Microsoft Project 2003-2019 file formats, including MPP, MPT, and XML.
### Is Aspose.Tasks compatible with Java frameworks like Spring?
Yes, Aspose.Tasks can be seamlessly integrated into Java frameworks like Spring for enterprise-grade applications.
### Can I customize project data fields using Aspose.Tasks?
Absolutely, Aspose.Tasks offers extensive APIs for customizing project data fields according to your requirements.
### Does Aspose.Tasks provide support and documentation for developers?
Yes, Aspose.Tasks offers comprehensive documentation and a dedicated support forum to assist developers with any queries or issues they encounter.

---
title: Read Timephased Data for Resources in Aspose.Tasks
linktitle: Read Timephased Data for Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to extract timephased data from MS Project resources using Aspose.Tasks for Java. Step-by-step tutorial.
type: docs
weight: 15
url: /java/resource-management/read-timephased-data/
---
## Introduction
In this tutorial, we'll guide you through the process of reading timephased data for MS Project resources using Aspose.Tasks for Java. This library provides powerful functionalities for managing Microsoft Project files programmatically.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system. You can download it from the [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) and follow the installation instructions.
2. Aspose.Tasks for Java Library: Download the Aspose.Tasks for Java library from the [download page](https://releases.aspose.com/tasks/java/) and follow the installation instructions provided in the documentation.

## Import Packages
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## Step 1: Set up Data Directory
First, define the directory where your MS Project file is located.
```java
String dataDir = "Your Data Directory";
```
## Step 2: Read MS Project Template File
Specify the name of your MS Project template file.
```java
String fileName = "ResourceTimephasedData.mpp";
```
## Step 3: Read Input File as Project
Read the input file using Aspose.Tasks and load it as a Project object.
```java
Project project = new Project(dataDir + fileName);
```
## Step 4: Get Resource by ID
Retrieve the desired resource from the project by its unique identifier (ID).
```java
Resource resource = project.getResources().getByUid(1);
```
## Step 5: Print Timephased Data for Resource Work
Print the timephased data for resource work.
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## Step 6: Print Timephased Data for Resource Cost
Print the timephased data for resource cost.
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## Conclusion
In this tutorial, we have learned how to read timephased data for MS Project resources using Aspose.Tasks for Java. By following these steps, you can efficiently extract valuable information from your project files programmatically.
## FAQ's
### Can Aspose.Tasks handle other types of project files apart from Microsoft Project?
Yes, Aspose.Tasks supports various file formats, including MPP, XML, and CSV.
### Is Aspose.Tasks compatible with different Java development environments?
Yes, Aspose.Tasks is compatible with all major Java IDEs and frameworks.
### Can I manipulate project data using Aspose.Tasks?
Absolutely, Aspose.Tasks provides extensive APIs for creating, modifying, and analyzing project data.
### Is Aspose.Tasks suitable for enterprise-level projects?
Yes, Aspose.Tasks is widely used in enterprise environments due to its reliability and scalability.
### Where can I find support if I encounter issues while using Aspose.Tasks?
You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for assistance from the community and support team.

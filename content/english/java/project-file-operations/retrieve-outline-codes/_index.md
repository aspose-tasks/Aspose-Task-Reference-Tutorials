---
title: Retrieve MS Project Outline Codes in Aspose.Tasks
linktitle: Retrieve Outline Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to retrieve Microsoft Project outline codes programmatically using Aspose.Tasks for Java. Enhance your project management capabilities.
type: docs
weight: 15
url: /java/project-file-operations/retrieve-outline-codes/
---
## Introduction
In this tutorial, we'll learn how to retrieve Microsoft Project outline codes using Aspose.Tasks for Java. Outline codes in MS Project provide a structured way to categorize and organize project tasks, resources, and assignments. Aspose.Tasks is a powerful Java library that allows developers to manipulate and manage Microsoft Project files programmatically.
## Prerequisites
Before we begin, ensure you have the following prerequisites set up:
### 1. Java Development Environment
Make sure you have Java Development Kit (JDK) installed on your system. You can download and install JDK from the official Oracle website.
### 2. Aspose.Tasks Library
Download and include the Aspose.Tasks library in your Java project. You can download the library from the [Aspose.Tasks for Java Download Page](https://releases.aspose.com/tasks/java/).
## Import Packages
First, import the necessary packages from Aspose.Tasks in your Java code:
```java
import com.aspose.tasks.OutlineCodeDefinition;
import com.aspose.tasks.OutlineMask;
import com.aspose.tasks.OutlineValue;
import com.aspose.tasks.Project;
```
Now let's break down the provided example code into multiple steps:
## Step 1: Load the Project
```java
String projectName = "ProjectFile.mpp";
Project project = new Project(projectName);
```
In this step, we load the Microsoft Project file into a `Project` object using the provided file name.
## Step 2: Retrieve Outline Codes
```java
for (OutlineCodeDefinition ocd : project.getOutlineCodes()) {
```
We iterate through each outline code definition in the project.
## Step 3: Access Outline Code Properties
```java
System.out.println("Alias = " + ocd.getAlias());
System.out.println("Field Id = " + ocd.getFieldId());
System.out.println("Field Name = " + ocd.getFieldName());
```
We retrieve and print various properties of the outline code definition such as Alias, Field ID, and Field Name.
## Step 4: Check Enterprise Custom Code
```java
if (ocd.getEnterprise()) {
    System.out.println("It is an enterprise custom outline code.");
} else {
    System.out.println("It is not an enterprise custom outline code.");
}
```
We check if the outline code is an enterprise custom code and print the result accordingly.
## Step 5: Display Outline Code Masks
```java
for (OutlineMask m1 : ocd.getMasks()) {
    System.out.println("Level of a mask = " + m1.getLevel());
    System.out.println("Mask = " + m1.toString());
}
```
We iterate through each mask associated with the outline code and print its level and mask value.
## Step 6: Display Outline Code Values
```java
for (OutlineValue v1 : ocd.getValues()) {
    System.out.println("Description of outline value = " + v1.getDescription());
    System.out.println("Value Id = " + v1.getValueId());
    System.out.println("Value = " + v1.getValue());
    System.out.println("Type = " + v1.getType());
}
```
We iterate through each outline code value and print its description, value ID, value, and type.
## Conclusion
In this tutorial, we have learned how to retrieve MS Project outline codes using Aspose.Tasks for Java. By following the provided steps, you can effectively access and manipulate outline codes in your Java applications, enabling advanced project management capabilities.
## FAQ's
### Q1: Can I use Aspose.Tasks for Java to modify outline codes in a Project file?
A: Yes, Aspose.Tasks for Java provides APIs to modify outline codes in MS Project files programmatically.
### Q2: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can download a free trial version of Aspose.Tasks for Java from the [Aspose.Tasks website](https://releases.aspose.com/).
### Q3: How can I get technical support for Aspose.Tasks for Java?
A: You can get technical support by visiting the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) and posting your queries there.
### Q4: Can I purchase a temporary license for Aspose.Tasks for Java?
A: Yes, you can purchase a temporary license for Aspose.Tasks for Java from the [purchase page](https://purchase.aspose.com/temporary-license/).
### Q5: Where can I find the complete documentation for Aspose.Tasks for Java?
A: You can refer to the [documentation](https://reference.aspose.com/tasks/java/) for detailed information on using Aspose.Tasks for Java.

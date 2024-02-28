---
title: MS Project Formulas with Aspose.Tasks for Java
linktitle: Work with Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to manipulate MS Project files in Java using Aspose.Tasks library. Create, modify, and calculate attributes with ease.
type: docs
weight: 11
url: /java/formulas/work-with-formulas/
---
## Introduction
In this tutorial, we'll delve into working with MS Project Formulas using Aspose.Tasks for Java. Aspose.Tasks is a powerful library that enables developers to manipulate Microsoft Project files programmatically. With its extensive features, you can easily create, read, modify, and convert project files in Java applications.
## Prerequisites
Before we begin, ensure you have the following prerequisites set up:
### Java Development Environment
Make sure you have a Java Development Kit (JDK) installed on your system. You can download and install the latest JDK from the official Oracle website.
### Aspose.Tasks Library
You need to have the Aspose.Tasks library added to your Java project. You can download the library from the [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) and include it in your project's dependencies.

## Import Packages
Before diving into the examples, import the necessary packages to your Java code:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Let's break down the example provided into multiple steps:
## Step 1: Create a Test Project with Custom Field
```java
Project project = CreateTestProjectWithCustomField();
```
First, create a test project with a custom field using the `CreateTestProjectWithCustomField()` method. This method will return a Project object representing the newly created project.
## Step 2: Define an Extended Attribute Definition
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
Retrieve the extended attribute definition from the project and set its alias and formula. In this example, we're defining an attribute to calculate the number of days from the finish date to the deadline.
## Step 3: Set Deadline for a Task
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
Create a Calendar object and set the deadline date. Then, retrieve a task from the project and set its deadline using the Calendar object.
## Step 4: Save the Project
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
Finally, save the project to a file with the specified name and format. In this case, we're saving it as an MPP file.

## Conclusion
In this tutorial, we've learned how to work with MS Project Formulas using Aspose.Tasks for Java. By following these steps, you can effectively manipulate project files programmatically, adding custom fields and calculating attributes based on formulas.

## FAQ's
### Q: Can I use Aspose.Tasks with other programming languages?
A: Yes, Aspose.Tasks supports various programming languages including Java, .NET, and more.
### Q: Is there a free trial available for Aspose.Tasks?
A: Yes, you can download a free trial of Aspose.Tasks from [here](https://releases.aspose.com/).
### Q: Where can I find documentation for Aspose.Tasks?
A: You can find the documentation for Aspose.Tasks [here](https://reference.aspose.com/tasks/java/).
### Q: How can I get support for Aspose.Tasks?
A: For support, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
### Q: Do I need a temporary license for using Aspose.Tasks?
A: If you require additional features, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/).

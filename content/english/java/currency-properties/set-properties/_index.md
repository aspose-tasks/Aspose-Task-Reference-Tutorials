---
title: Set Currency Properties in Aspose.Tasks Projects
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
description: Learn how to set currency properties in Aspose.Tasks projects using Java. Manipulate Microsoft Project files effortlessly.
type: docs
weight: 11
url: /java/currency-properties/set-properties/
---
## Introduction
In this tutorial, we'll explore how to set currency properties in Aspose.Tasks projects using Java. Aspose.Tasks is a powerful Java library that allows developers to manipulate Microsoft Project files programmatically.
## Prerequisites
Before we begin, ensure you have the following:
1. Java Development Kit (JDK): Ensure you have JDK installed on your system.
2. Aspose.Tasks for Java Library: Download and install the Aspose.Tasks for Java library from the [download link](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Choose your preferred IDE such as Eclipse or IntelliJ IDEA.
## Import Packages
First, let's import the necessary packages to work with Aspose.Tasks in Java.
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## Step 1: Set Data Directory
Set the data directory where your project files are located.
```java
String dataDir = "Your Data Directory";
```
## Step 2: Create Project Instance
Create a new project instance using Aspose.Tasks.
```java
Project project = new Project();
```
## Step 3: Set Currency Properties
Now, let's set the currency properties for the project.
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## Step 4: Save the Project
Save the project with the updated currency properties.
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## Step 5: Display Completion Message
Display a message indicating the successful completion of the process.
```java
System.out.println("Process completed Successfully");
```
Congratulations! You've successfully set currency properties in an Aspose.Tasks project using Java.
## Conclusion
In this tutorial, we learned how to use Aspose.Tasks for Java to set currency properties in project files. With Aspose.Tasks, developers can efficiently manipulate project data, making it a valuable tool for project management applications.
## FAQ's
### Can I set multiple currencies in a single project using Aspose.Tasks?
Yes, Aspose.Tasks allows you to handle multiple currencies within a single project file.
### Is Aspose.Tasks compatible with different versions of Microsoft Project files?
Yes, Aspose.Tasks supports various versions of Microsoft Project files, ensuring compatibility across different environments.
### Does Aspose.Tasks provide support for custom currency formats?
Absolutely, Aspose.Tasks offers flexibility in defining custom currency formats to meet specific project requirements.
### Can I integrate Aspose.Tasks with other Java libraries or frameworks?
Yes, Aspose.Tasks can be seamlessly integrated with other Java libraries and frameworks, enhancing its functionality and versatility.
### Where can I find additional support or assistance for Aspose.Tasks?
For additional support, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), where you can find helpful resources and engage with the community.

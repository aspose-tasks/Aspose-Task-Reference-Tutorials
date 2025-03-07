---
title: Write MPP Project Summary in Aspose.Tasks
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to write MPP project summaries in Java using Aspose.Tasks. Set and retrieve project information effortlessly.
weight: 27
url: /java/project-file-operations/write-mpp-project-summary/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Write MPP Project Summary in Aspose.Tasks

## Introduction
In this tutorial, we will learn how to utilize Aspose.Tasks for Java to write MPP project summaries. Aspose.Tasks is a powerful Java library for working with Microsoft Project files. By following the steps outlined below, you will be able to set and retrieve various summary information about a project using this library.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system.
2. Aspose.Tasks for Java: Download and install the Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): Choose your preferred IDE for Java development, such as IntelliJ IDEA, Eclipse, or NetBeans.

## Import Packages
Firstly, import the necessary packages into your Java class:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```
## Step 1: Set Up Project and Define Summary Information
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
## Step 2: Save Project Summary Information
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
## Step 3: Read Project Summary Information
```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## Conclusion
In this tutorial, we've covered how to write MPP project summaries using Aspose.Tasks for Java. By following these steps, you can efficiently set and retrieve various summary information about your project files. Aspose.Tasks simplifies the process of working with Microsoft Project files in Java applications, offering robust functionality and ease of use.
## FAQ's
### Q: Can I use Aspose.Tasks for Java with other Java libraries?
A: Yes, Aspose.Tasks for Java can be seamlessly integrated with other Java libraries to enhance your project management capabilities.
### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can download a free trial version from [here](https://releases.aspose.com/).
### Q: How frequently is Aspose.Tasks for Java updated?
A: Aspose.Tasks for Java is regularly updated to ensure compatibility with the latest versions of Java and Microsoft Project files.
### Q: Can I customize the project summary information further?
A: Absolutely, Aspose.Tasks for Java provides extensive options for customizing project summary information according to your specific requirements.
### Q: Where can I get support for Aspose.Tasks for Java?
A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

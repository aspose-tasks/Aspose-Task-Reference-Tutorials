---
title: Weekday Properties in Aspose.Tasks
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn to manage weekday properties efficiently in Aspose.Tasks for Java. Customize week start dates, days per month, and more with ease.
type: docs
weight: 25
url: /java/project-file-operations/weekday-properties/
---
## Introduction
Aspose.Tasks for Java is a powerful API that enables Java developers to work with Microsoft Project files without Microsoft Project installed on the machine. One of its key functionalities is managing weekday properties, allowing users to customize week start dates, days per month, minutes per day, and minutes per week. This tutorial will provide a detailed guide on how to utilize these features effectively.
## Prerequisites
Before diving into Aspose.Tasks for Java, ensure you have the following prerequisites:
### Java Development Kit (JDK)
Make sure you have JDK installed on your system. You can download and install the latest JDK from the official Oracle website.
### Aspose.Tasks for Java Library
Download and install the Aspose.Tasks for Java library from the website. You can access the download link [here](https://releases.aspose.com/tasks/java/).
### Integrated Development Environment (IDE)
Choose an IDE of your preference for Java development. Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.
## Import Packages
To get started, import the necessary Aspose.Tasks packages into your Java project. Here's how:

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

Now, let's break down the provided example into multiple steps for a better understanding.
## Step 1: Load Project File
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
This step involves loading a Project file named "project.mpp" from the specified data directory.
## Step 2: Display Weekday Properties
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
Here, we retrieve and print the week start date, days per month, minutes per day, and minutes per week properties of the loaded project.
## Step 3: Setting Weekday Properties
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
This step involves creating a new project instance and setting custom weekday properties such as the week start day, days per month, minutes per day, and minutes per week.
## Step 4: Save Project
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
Finally, we save the modified project with the updated weekday properties as an XML file.
## Step 5: Display Result
```java
System.out.println("Process completed Successfully");
```
This step confirms the successful completion of the process.
## Conclusion
Mastering weekday properties in Aspose.Tasks for Java is crucial for effective project management. By following this tutorial, you've learned how to manipulate and customize weekday properties effortlessly. Explore further documentation and examples to enhance your project management capabilities.
## FAQ's
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures with ease.
### Q: Is Aspose.Tasks for Java compatible with different versions of Microsoft Project files?
A: Absolutely, Aspose.Tasks for Java supports various versions of Microsoft Project files, ensuring compatibility across platforms.
### Q: Can I integrate Aspose.Tasks for Java into my existing Java applications?
A: Yes, Aspose.Tasks for Java offers seamless integration capabilities, allowing you to enhance your Java applications with powerful project management features.
### Q: Does Aspose.Tasks for Java provide documentation and support?
A: Yes, you can access extensive documentation and community support for Aspose.Tasks for Java on their [website](https://releases.aspose.com/).
### Q: Is there a free trial available for Aspose.Tasks for Java?
A: Yes, you can download a free trial version of Aspose.Tasks for Java from their [website](https://reference.aspose.com/tasks/java/) to explore its features before making a purchase.

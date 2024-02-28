---
title: Setting MS Project Attributes for New Tasks in Aspose.Tasks
linktitle: Set Attributes for New Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to set MS Project attributes for new tasks using Aspose.Tasks for Java. Customize task properties effortlessly with this comprehensive guide.
type: docs
weight: 21
url: /java/project-file-operations/set-attributes-new-tasks/
---
## Introduction
Welcome to our comprehensive tutorial on setting MS Project attributes for new tasks in Aspose.Tasks for Java! In this guide, we will walk you through the process step by step, ensuring that you can easily manage and customize your tasks with this powerful Java library.
## Prerequisites
Before we dive into the tutorial, make sure you have the following prerequisites in place:
1. Java Development Environment: Ensure that you have Java installed on your system and that you are familiar with basic Java programming concepts.
2. Aspose.Tasks for Java Library: Download and install the Aspose.Tasks for Java library from the [download link](https://releases.aspose.com/tasks/java/).
3. Java IDE: Choose a Java Integrated Development Environment (IDE) such as Eclipse or IntelliJ IDEA for coding.

## Import Packages
Before we begin setting MS Project attributes for new tasks, let's import the necessary packages:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## Step 1: Define the Data Directory
First, specify the path to the directory where you want to save your project files:
```java
String dataDir = "Your Data Directory";
```
Replace `"Your Data Directory"` with the path to your desired directory.
## Step 2: Create a Project Instance
Instantiate a new Project object to begin working with your project:
```java
Project prj = new Project();
```
This creates a new project instance.
## Step 3: Set New Task Property
Now, let's set the start date for new tasks. In this example, we set it to the current date:
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
This line sets the property `NEW_TASK_START_DATE` to `TaskStartDateType.CurrentDate`.
## Step 4: Save the Project
Save the project with the new task attributes in XML format:
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
This line saves the project with the specified file name in the directory defined earlier.
## Step 5: Display Result
Finally, let's print a message to confirm that the project file was generated successfully:
```java
System.out.println("Project file generated Successfully");
```
This line displays the success message in the console.

## Conclusion
Congratulations! You've successfully learned how to set MS Project attributes for new tasks using Aspose.Tasks for Java. With this knowledge, you can now customize task properties according to your requirements, enhancing your project management capabilities.
## FAQ's
### Q: Can I use Aspose.Tasks for Java to manipulate existing project files?
A: Yes, Aspose.Tasks for Java provides extensive functionality to manipulate existing project files, including reading, modifying, and saving them in various formats.
### Q: Where can I find more documentation and resources for Aspose.Tasks for Java?
A: You can explore the documentation and resources on the [Aspose.Tasks for Java documentation page](https://reference.aspose.com/tasks/java/).
### Q: Is there a free trial available for Aspose.Tasks for Java?
A: Yes, you can download a free trial version of Aspose.Tasks for Java from [here](https://releases.aspose.com/).
### Q: How can I get temporary licenses for Aspose.Tasks for Java?
A: Temporary licenses for Aspose.Tasks for Java can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/).
### Q: Where can I get support for any issues or queries related to Aspose.Tasks for Java?
A: You can get support and interact with the community on the [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15).

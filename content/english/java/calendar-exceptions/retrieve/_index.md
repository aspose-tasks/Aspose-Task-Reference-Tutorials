---
title: Retrieve Calendar Exceptions with Aspose.Tasks
linktitle: Retrieve Calendar Exceptions with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to retrieve calendar exceptions from MS Project using Aspose.Tasks for Java. Step-by-step tutorial for seamless integration.
type: docs
weight: 13
url: /java/calendar-exceptions/retrieve/
---
## Introduction
In this tutorial, we will explore how to retrieve calendar exceptions from MS Project using the Aspose.Tasks library for Java. Aspose.Tasks is a powerful tool that allows developers to manipulate Microsoft Project files programmatically. We will guide you through the process step by step, breaking down each example into multiple steps for easy understanding.
## Prerequisites
Before we begin, make sure you have the following prerequisites:
1. Java Development Kit (JDK): Ensure you have JDK installed on your system.
2. Aspose.Tasks for Java: Download and install Aspose.Tasks for Java from [here](https://releases.aspose.com/tasks/java/).
3. Integrated Development Environment (IDE): You can use any IDE of your choice, such as IntelliJ IDEA or Eclipse.

## Import Packages
First, you need to import the necessary packages to work with Aspose.Tasks:
```java
import com.aspose.tasks.*;
```
## Step 1: Set Up Your Data Directory
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
Ensure to replace `"Your Data Directory"` with the path to your directory containing the MS Project file.
## Step 2: Load MS Project File
```java
Project project = new Project(dataDir + "project.mpp");
```
This line initializes a new `Project` object by loading the MS Project file specified by the path.
## Step 3: Retrieve Calendar Exceptions
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
Here, we iterate through each calendar in the project and then through each calendar exception within that calendar. We print out the start and end dates of each exception.

## Conclusion
In this tutorial, we have learned how to retrieve calendar exceptions from MS Project using Aspose.Tasks for Java. By following these simple steps, you can seamlessly integrate this functionality into your Java applications.
## Frequently Asked Questions
### Can Aspose.Tasks handle different versions of MS Project files?
Yes, Aspose.Tasks supports various versions of MS Project files, including MPP, MPT, and XML formats.
### Is there a free trial available for Aspose.Tasks?
Yes, you can download a free trial of Aspose.Tasks from [here](https://releases.aspose.com/).
### Where can I find documentation for Aspose.Tasks for Java?
You can refer to the documentation [here](https://reference.aspose.com/tasks/java/).
### How can I get support for Aspose.Tasks?
You can get support from the community forum [here](https://forum.aspose.com/c/tasks/15).
### Is there an option for temporary licenses for Aspose.Tasks?
Yes, you can obtain temporary licenses from [here](https://purchase.aspose.com/temporary-license/).

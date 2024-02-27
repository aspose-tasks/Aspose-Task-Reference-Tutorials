---
title: Get Working Hours from Calendar using Aspose.Tasks
linktitle: Get Working Hours from Calendar using Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Extract working hours from MS Project calendars easily with Aspose.Tasks for Java. Simplify project management tasks.
type: docs
weight: 13
url: /java/calendars/working-hours/
---
## Introduction
Managing project calendars and extracting working hours is essential for effective project management. Aspose.Tasks for Java provides robust functionality to retrieve working hours from MS Project calendars effortlessly. In this tutorial, we will guide you through the process step by step.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
1. Java Development Kit (JDK) installed on your system.
2. Aspose.Tasks for Java library downloaded and added to your project. You can download it from [here](https://releases.aspose.com/tasks/java/).
3. Basic understanding of Java programming language.
## Import Packages
First, import the necessary packages to work with Aspose.Tasks for Java:
```java
import com.aspose.tasks.*;
```
## Step 1: Load Project File
Start by loading your MS Project file:
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## Step 2: Retrieve Task and Calendar Information
Extract task and calendar details from the project:
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## Step 3: Define Start and End Dates
Set up start and end dates for the task:
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## Step 4: Iterate Through Dates
Iterate through dates within the task duration:
```java
java.util.Calendar tempDate = calStartDate;
```
## Step 5: Calculate Duration
Calculate duration in minutes, hours, and days:
```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```
## Conclusion
In this tutorial, we've covered how to retrieve working hours from an MS Project calendar using Aspose.Tasks for Java. By following these steps, you can efficiently manage project schedules and calculate task durations with ease.
## FAQ's
### Q: Can Aspose.Tasks for Java handle complex project structures?
A: Yes, Aspose.Tasks for Java provides comprehensive support for handling complex project structures, including tasks, resources, and calendars.
### Q: Is Aspose.Tasks for Java compatible with different versions of MS Project?
A: Absolutely, Aspose.Tasks for Java supports various versions of MS Project, ensuring compatibility across different environments.
### Q: Can I customize working hours and holidays in project calendars?
A: Yes, you can easily customize working hours and holidays according to your project requirements using Aspose.Tasks for Java APIs.
### Q: Does Aspose.Tasks for Java offer support and documentation?
A: Yes, Aspose.Tasks for Java provides extensive documentation and dedicated support forums to assist developers in utilizing its features effectively.
### Q: Is there a trial version available for Aspose.Tasks for Java?
A: Yes, you can access a free trial version of Aspose.Tasks for Java from [here](https://releases.aspose.com/).

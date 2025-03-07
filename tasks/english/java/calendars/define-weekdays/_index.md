---
title: Define Weekdays in Calendar with Aspose.Tasks
linktitle: Define Weekdays in Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to define weekdays in MS Project Calendar using Aspose.Tasks for Java. Customize working days and timings effortlessly.
weight: 12
url: /java/calendars/define-weekdays/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Define Weekdays in Calendar with Aspose.Tasks

## Introduction
In this tutorial, we will walk through the process of defining weekdays in an MS Project Calendar using Aspose.Tasks for Java. Aspose.Tasks is a powerful Java library that enables developers to manipulate Microsoft Project files programmatically.
## Prerequisites
Before we begin, ensure you have the following prerequisites in place:
1. Java Development Kit (JDK): Make sure you have JDK installed on your system. You can download it from the [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) if you haven't already.
2. Aspose.Tasks for Java Library: Download and install the Aspose.Tasks for Java library from the [download page](https://releases.aspose.com/tasks/java/). Follow the installation instructions provided in the documentation.

## Import Packages
To start, import the necessary packages required for working with Aspose.Tasks in your Java project:
```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```
## Step 1: Create a Project Instance
Instantiate a Project object, which represents the MS Project file you will be working with:
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```
## Step 2: Define Calendar
Create a new calendar instance and add it to the project:
```java
Calendar cal = prj.getCalendars().add("Calendar1");
```
## Step 3: Add Working Days
Define the working days by adding Monday through Thursday with default timings:
```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```
## Step 4: Set Custom Working Day
Define Saturday and Sunday as working days:
```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```
## Step 5: Set Short Working Day
Set Friday as a short working day with custom working times:
```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```
## Step 6: Save the Project
Save the modified project to an XML file:
```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## Conclusion
Congratulations! You've successfully defined weekdays in an MS Project Calendar using Aspose.Tasks for Java. You can now integrate this functionality into your Java applications to manipulate MS Project files programmatically.
## FAQ's
### Q1: Can I define custom non-working days using Aspose.Tasks for Java?
A: Yes, you can define custom non-working days by setting the `DayWorking` property to `false` for the respective weekday.
### Q2: How can I add holidays to the calendar?
A: You can add holidays by creating instances of `CalendarExceptions` and specifying the non-working dates.
### Q3: Is Aspose.Tasks compatible with different versions of MS Project files?
A: Yes, Aspose.Tasks supports various versions of MS Project files, including MPP, MPT, and XML formats.
### Q4: Can I modify existing calendars in an MS Project file?
A: Yes, you can load an existing project with calendars, make modifications, and then save the changes back to the original file.
### Q5: Does Aspose.Tasks provide support for recurring tasks?
A: Yes, Aspose.Tasks allows you to work with recurring tasks, including defining their recurrence patterns and durations.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

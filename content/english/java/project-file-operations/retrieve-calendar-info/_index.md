---
title: Retrieve MS Project Calendar Info in Aspose.Tasks
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to retrieve MS Project calendar info using Aspose.Tasks for Java. Step-by-step guide for accessing calendar details programmatically.
type: docs
weight: 14
url: /java/project-file-operations/retrieve-calendar-info/
---
## Introduction
In this tutorial, we'll explore how to retrieve calendar information from Microsoft Project files using the Aspose.Tasks for Java library. Aspose.Tasks provides powerful features to manipulate project data, including accessing calendar details such as working days and hours.
## Prerequisites
Before we begin, make sure you have the following:
- Basic knowledge of Java programming.
- Java Development Kit (JDK) installed on your system.
- Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
## Import Packages
First, you need to import the necessary packages in your Java code to use Aspose.Tasks functionalities.
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
Now let's break down the provided example into multiple steps for a better understanding.
## Step 1: Set Data Directory
```java
String dataDir = "Your Data Directory";
```
Replace `"Your Data Directory"` with the path to your project files directory.
## Step 2: Define Time Units
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
These constants represent time units in microseconds.
## Step 3: Create Project Instance
```java
Project project = new Project(dataDir + "project.mpp");
```
This line creates an instance of the `Project` class, initializing it with the path to the project file (`project.mpp`).
## Step 4: Retrieve Calendars Information
```java
CalendarCollection alCals = project.getCalendars();
```
Here, we retrieve a collection of calendars present in the project file.
## Step 5: Iterate Through Calendars
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
This loop iterates through each calendar and prints its UID, name, and working days with respective working hours.
## Step 6: Display Completion Message
```java
System.out.println("Process completed Successfully");
```
Finally, a message is displayed indicating the completion of the process.
## Conclusion
In this tutorial, we learned how to retrieve calendar information from MS Project files using Aspose.Tasks for Java. By following these steps, you can efficiently access and manipulate project data in your Java applications.

## FAQ's
### Q: Can I use Aspose.Tasks with other programming languages?
A: Yes, Aspose.Tasks supports multiple platforms and programming languages, including .NET, C++, Python, and Java.
### Q: Is there a free trial available for Aspose.Tasks?
A: Yes, you can download a free trial version from [here](https://releases.aspose.com/).
### Q: How can I get support for Aspose.Tasks?
A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
### Q: Can I purchase a temporary license for Aspose.Tasks?
A: Yes, temporary licenses are available for purchase [here](https://purchase.aspose.com/temporary-license/).
### Q: Where can I find detailed documentation for Aspose.Tasks?
A: You can refer to the documentation [here](https://reference.aspose.com/tasks/java/).

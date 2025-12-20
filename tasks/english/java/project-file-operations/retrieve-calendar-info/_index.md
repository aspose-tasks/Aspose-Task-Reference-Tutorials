---
title: "How to Use Aspose.Tasks to Retrieve MS Project Calendar Info"
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: "Learn how to use Aspose.Tasks to extract project calendar details from Microsoft Project files using Java. Step‑by‑step guide with code examples."
weight: 14
url: /java/project-file-operations/retrieve-calendar-info/
date: 2025-12-20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Use Aspose.Tasks to Retrieve MS Project Calendar Info

## Introduction
In this tutorial, **you’ll discover how to use Aspose.Tasks** to programmatically retrieve calendar information from Microsoft Project files. Accessing calendar data such as working days, hours, and exceptions is essential when you need to **extract project calendar** details for reporting, integration, or custom scheduling logic. Let’s walk through the process step by step.

## Quick Answers
- **What library does this tutorial use?** Aspose.Tasks for Java.  
- **Which primary keyword is covered?** *how to use aspose.tasks*.  
- **What can you extract?** Project calendars, including working days and hours.  
- **Do I need a license?** A free trial is available; a license is required for production.  
- **What Java version is supported?** Java 8 or higher.

## Why extract project calendar information?
Project calendars drive task dates, resource allocations, and overall timeline calculations. By extracting this data you can:
- Generate custom reports that reflect actual working schedules.  
- Synchronize Microsoft Project timelines with external systems (ERP, BI, etc.).  
- Perform what‑if analysis by modifying calendar settings programmatically.

## Prerequisites
Before we begin, ensure you have:

- Basic knowledge of Java programming.  
- Java Development Kit (JDK) installed on your system.  
- Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).

## Import Packages
First, import the necessary Aspose.Tasks classes into your Java project.

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## Step 1: Set Data Directory
Define the folder that contains your *.mpp* file.

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path to the folder where **project.mpp** resides.

## Step 2: Define Time Units
Create constants that help convert the internal time representation to human‑readable hours.

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

These values are expressed in microseconds, which is how Aspose.Tasks stores time internally.

## Step 3: Create Project Instance
Load the Microsoft Project file into a `Project` object.

```java
Project project = new Project(dataDir + "project.mpp");
```

The `Project` constructor parses the *.mpp* file and makes all project data, including calendars, accessible through the API.

## Step 4: Retrieve Calendars Information
Obtain the collection of calendars defined in the project.

```java
CalendarCollection alCals = project.getCalendars();
```

A project can contain multiple calendars (standard, resource, and custom calendars). This collection gives you access to each one.

## Step 5: Iterate Through Calendars
Loop through every calendar, display its UID, name, and the working days with corresponding hours.

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

The inner loop checks each `WeekDay` object. If the day is marked as working, it prints the day type (Monday, Tuesday, …) together with the calculated working hours.

## Step 6: Display Completion Message
Signal that the extraction process has finished.

```java
System.out.println("Process completed Successfully");
```

## Conclusion
By following these steps, **you now know how to use Aspose.Tasks to extract project calendar** information from an MS Project file using Java. You can integrate this logic into larger applications, automate reporting, or synchronize schedules with other enterprise systems.

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks supports multiple platforms and programming languages, including .NET, C++, Python, and Java.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Yes, you can download a free trial version from [here](https://releases.aspose.com/).

**Q: How can I get support for Aspose.Tasks?**  
A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

**Q: Can I purchase a temporary license for Aspose.Tasks?**  
A: Yes, temporary licenses are available for purchase [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find detailed documentation for Aspose.Tasks?**  
A: You can refer to the documentation [here](https://reference.aspose.com/tasks/java/).

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
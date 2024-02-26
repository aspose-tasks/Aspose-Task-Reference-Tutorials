---
title: Manage Calendar Properties in Aspose.Tasks
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 10
url: /java/calendars/properties/
---

## Complete Source Code
```java
/*
 * Copyright 2001-2022 Aspose Pty Ltd. All Rights Reserved.
 *
 * This file is part of Aspose.Tasks. The source code in this file
 * is only intended as a supplement to the documentation, and is provided
 * "as is", without warranty of any kind, either expressed or implied.
 */



import com.aspose.tasks.*;


public class CalendarProperties {
    public static void main(String[] args) {
        // ExStart: CalendarProperties
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        long OneSec = 1000; // 1000 milliseconds
        long OneMin = 60 * OneSec;
        long OneHour = 60 * OneMin;

        Project project = new Project(dataDir + "project.xml");

        for (Calendar cal : project.getCalendars()) {
            if (cal.getName() == null) {
                continue;
            }

            System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());

            // Show if it is has a base calendar
            System.out.print("Base Calendar: ");
            System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());

            for (WeekDay wd : cal.getWeekDays()) {
                double ts = wd.getWorkingTime();
                System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
            }
        }
        // ExEnd: CalendarProperties
    }
}

```

---
title: Retrieve Calendar Info in Aspose.Tasks
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 14
url: /java/project-file-operations/retrieve-calendar-info/
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



import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;


public class RetrieveCalendarInfo {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        long OneSec = 10000000;//microsecond * 10
        long OneMin = 60 * OneSec;
        long OneHour = 60 * OneMin;

        //Create a project reader instance
        Project project = new Project(dataDir + "project.mpp");

        //Retrieve Calendars Information
        CalendarCollection alCals = project.getCalendars();

        for (Calendar cal : alCals) {
            if (cal.getName() != null) {
                System.out.println("Calendar UID : " + cal.getUid());
                System.out.println("Calendar Name : " + cal.getName());

                WeekDayCollection alDays = cal.getWeekDays();
                for (WeekDay wd : alDays) {
                    double ts = wd.getWorkingTime();        //milliseconds
                    double time = ts / (OneHour);
                    if (wd.getDayWorking()) {
                        System.out.print(wd.getDayType() + ":");
                        System.out.print("Working Time:" + time + " Hours");
                        System.out.println(", Ticks = " + ts);
                    }
                }
            }
        }

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```

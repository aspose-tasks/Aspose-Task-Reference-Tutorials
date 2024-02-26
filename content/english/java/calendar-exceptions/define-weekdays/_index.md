---
title: Define Weekdays for Calendar Exceptions with Aspose.Tasks
linktitle: Define Weekdays for Calendar Exceptions with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/calendar-exceptions/define-weekdays/
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


import java.util.GregorianCalendar;

public class DefineWeekdaysForExceptions {
    public static void main(String[] args) {
        // ExStart: DefineWeekDaysForExceptions
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        // Create a project instance
        Project project = new Project();

        // Define Calendar
        Calendar cal = project.getCalendars().add("Calendar1");

        // Define week days exception for Christmas
        CalendarException except = new CalendarException();
        except.setEnteredByOccurrences(false);
        except.setFromDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 24, 0, 0, 0).getTime());
        except.setToDate(new GregorianCalendar(2009, java.util.Calendar.DECEMBER, 31, 23, 59, 0).getTime());
        except.setType(CalendarExceptionType.Daily);
        except.setDayWorking(false);
        cal.getExceptions().add(except);

        // Save the Project
        project.save(dataDir + "project.xml", SaveFileFormat.Xml);
        // ExEnd: DefineWeekDaysForExceptions
    }
}





```

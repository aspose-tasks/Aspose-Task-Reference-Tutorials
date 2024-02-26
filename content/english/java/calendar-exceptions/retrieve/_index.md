---
title: Retrieve Calendar Exceptions with Aspose.Tasks
linktitle: Retrieve Calendar Exceptions with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 13
url: /java/calendar-exceptions/retrieve/
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


public class RetrieveCalendarExceptions {
    public static void main(String[] args) {
        // ExStart: RetrieveCalendarExceptions
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "project.mpp");

        for (Calendar cal : project.getCalendars()) {
            for (CalendarException calExc : cal.getExceptions()) {
                System.out.println("From: " + calExc.getFromDate().toString());
                System.out.println("To: " + calExc.getToDate().toString());
            }
        }
        // ExEnd: RetrieveCalendarExceptions
    }
}





```

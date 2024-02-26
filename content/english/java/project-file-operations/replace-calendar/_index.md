---
title: Replace Calendar in Aspose.Tasks
linktitle: Replace Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 12
url: /java/project-file-operations/replace-calendar/
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

public class ReplaceCalendar {
    public static void main(String[] args) {
        Project project = new Project();

        // Add a calendar to the project
        project.getCalendars().add("Cal 1");
        Calendar newCal = project.getCalendars().add("New Cal");

        CalendarCollection calColl = project.getCalendars();
        for (int i = calColl.size() - 1; i >= 0; i--) {
            Calendar c = calColl.get(i);
            if (c.getName().equals("Cal 1")) {
                calColl.remove(i);
                calColl.add("Standard", newCal);
                break;
            }
        }

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```

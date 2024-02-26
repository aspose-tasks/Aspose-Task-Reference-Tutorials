---
title: Manage Resources and Calendars in Aspose.Tasks
linktitle: Manage Resources and Calendars in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 17
url: /java/resource-management/resources-and-calendars/
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
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceCollection;
import com.aspose.tasks.Rsc;


public class ResourceAndCalendars {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        settingResourceCalendar();
        gettingResourceCalendar(dataDir);

        // Display result of conversion.
        System.out.println("Process completed Successfully");
    }

    public static void settingResourceCalendar() {
        Project project = new Project();
        Resource res = project.getResources().add("Resource1");

        // add standard calendar
        Calendar cal = project.getCalendars().add("Resource1");
        res.set(Rsc.CALENDAR, cal);
    }

    public static void gettingResourceCalendar(String dataDir) {
        Project project = new Project(dataDir + "ResourceCalendar.mpp");
        ResourceCollection alRes = project.getResources();
        for (Resource res : alRes) {
            if (res.get(Rsc.NAME) != null) {
                //code to display res.Calendar properties
            }
        }
    }
}



```

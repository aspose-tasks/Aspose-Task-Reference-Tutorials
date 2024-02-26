---
title: Make Standard Calendar in Aspose.Tasks
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 14
url: /java/calendars/make-standard/
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


public class MakeStandardCalendar {
    public static void main(String[] args) {
        // ExStart: MakeStandardCalendar
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //Create a project instance
        Project project = new Project();

        //Define Calendar and make it standard
        Calendar cal1 = project.getCalendars().add("My Cal");
        Calendar.makeStandardCalendar(cal1);

        //Save the Project
        project.save(dataDir + "project.xml", SaveFileFormat.Xml);

        //Display result of conversion.
        System.out.println("Process completed Successfully");
        // ExEnd: MakeStandardCalendar
    }
}





```

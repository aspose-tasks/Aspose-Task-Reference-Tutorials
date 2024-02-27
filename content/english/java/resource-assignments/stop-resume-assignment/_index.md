---
title: Stop and Resume Resource Assignments in Aspose.Tasks
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 23
url: /java/resource-assignments/stop-resume-assignment/
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



import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;


import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;

public class StopResumeAssignment {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");

        java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
        for (ResourceAssignment ra : prj.getResourceAssignments()) {
            if (ra.get(Asn.STOP).before(minDate)) {
                System.out.println("NA");
            } else {
                System.out.println(ra.get(Asn.STOP));
            }
            if (ra.get(Asn.RESUME).before(minDate)) {
                System.out.println("NA");
            } else {
                System.out.println(ra.get(Asn.RESUME));
            }
        }
    }
}





```
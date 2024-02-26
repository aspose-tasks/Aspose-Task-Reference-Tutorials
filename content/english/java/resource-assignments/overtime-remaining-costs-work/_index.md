---
title: Monitor Overtime, Remaining Costs, and Work in Aspose.Tasks
linktitle: Monitor Overtime, Remaining Costs, and Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 18
url: /java/resource-assignments/overtime-remaining-costs-work/
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


public class OvertimeRemainingCostsWork {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");

        for (ResourceAssignment ra : project.getResourceAssignments()) {
            System.out.println(ra.get(Asn.OVERTIME_COST));
            System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
            System.out.println(ra.get(Asn.REMAINING_COST));
            System.out.println(ra.get(Asn.REMAINING_WORK).toString());
            System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
            System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
        }
    }
}





```

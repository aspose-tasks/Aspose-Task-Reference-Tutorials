---
title: Deal with Variances in Aspose.Tasks
linktitle: Deal with Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 15
url: /java/resource-assignments/deal-with-variances/
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


public class DealingVariances {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");

        for (ResourceAssignment ra : project.getResourceAssignments()) {
            System.out.println(ra.get(Asn.WORK_VARIANCE));
            System.out.println(ra.get(Asn.COST_VARIANCE));
            System.out.println(ra.get(Asn.START_VARIANCE));
            System.out.println(ra.get(Asn.FINISH_VARIANCE));
        }
    }
}





```

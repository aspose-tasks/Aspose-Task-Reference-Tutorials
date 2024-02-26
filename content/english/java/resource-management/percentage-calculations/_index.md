---
title: Perform Percentage Calculations for Resources in Aspose.Tasks
linktitle: Perform Percentage Calculations for Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 14
url: /java/resource-management/percentage-calculations/
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



import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;


public class PercentageCalculations {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project prj = new Project(dataDir + "Software Development.mpp");
        for (Resource res : prj.getResources()) {
            if (res.get(Rsc.NAME) != null) {
                System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
            }
        }
    }
}





```

---
title: Write Updated Resource Data in Aspose.Tasks
linktitle: Write Updated Resource Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 21
url: /java/resource-management/write-updated-resource-data/
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
import com.aspose.tasks.SaveFileFormat;


import java.math.BigDecimal;

public class WriteUpdatedResourceData {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
        // File to write test project
        String resultFile = dataDir + "OutputMPP.mpp";

        Project project = new Project(file);
        Resource rsc = project.getResources().add("Rsc");
        rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
        rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
        rsc.set(Rsc.GROUP, "Workgroup1");

        //Save the Project
        project.save(resultFile, SaveFileFormat.Mpp);
    }
}





```

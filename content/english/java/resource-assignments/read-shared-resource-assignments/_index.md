---
title: Read Shared Resource Assignments in Aspose.Tasks
linktitle: Read Shared Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 19
url: /java/resource-assignments/read-shared-resource-assignments/
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


public class ReadSharedResourceAssignments {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        // ExStart: ReadSharedResourceAssignments
        // suppose `test.mpp` contains resource from resource pool and assignments from other projects
        Project project = new Project(dataDir + "ResourceCosts.mpp");
        Resource resource = project.getResources().getByUid(1);
        // Units are calculated using assignments from other projects.
        Double units = resource.get(Rsc.PEAK_UNITS);
        // ExEnd: ReadSharedResourceAssignments
    }
}

```

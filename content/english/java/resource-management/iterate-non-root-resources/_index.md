---
title: Iterate Over Non-Root Resources in Aspose.Tasks
linktitle: Iterate Over Non-Root Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 12
url: /java/resource-management/iterate-non-root-resources/
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


public class IterateOverNonRootResources {
    public static void main(String[] args) {
        // Shows how to use IsRoot property to skip root resource.

        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project prj = new Project(dataDir + "ResourceCosts.mpp");
        for (Resource res : prj.getResources()) {
            if (res.isRoot()) {
                continue;
            }
            System.out.println(res.get(Rsc.NAME));
        }
    }
}
```

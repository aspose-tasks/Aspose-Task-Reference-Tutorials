---
title: Assignment Budget Management in Aspose.Tasks
linktitle: Assignment Budget Management in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/resource-assignments/assignment-budget/
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


public class AssignmentBudget {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project prj = new Project(dataDir + "project.mpp");

        for (ResourceAssignment ra : prj.getResourceAssignments()) {
            System.out.println(ra.get(Asn.BUDGET_COST));
            System.out.println(ra.get(Asn.BUDGET_WORK).toString());
        }
    }
}





```

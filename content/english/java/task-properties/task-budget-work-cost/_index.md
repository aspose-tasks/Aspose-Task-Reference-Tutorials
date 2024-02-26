---
title: Budget, Work, and Cost Management for Tasks in Aspose.Tasks
linktitle: Budget, Work, and Cost Management for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 31
url: /java/task-properties/task-budget-work-cost/
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
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;


public class TaskBudgetWorkAndCost {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
        Task projSummary = project.getRootTask();

        System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
        System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));

        //Get resource by Uid
        Resource rsc = project.getResources().getByUid(2);

        //Display resource budget work
        System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));

        //Get next resource by Uid
        rsc = project.getResources().getByUid(2);

        //Display resource budget cost
        System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));

        for (ResourceAssignment assn : projSummary.getAssignments()) {
            if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
                System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
            } else {
                System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
            }
        }
    }
}





```

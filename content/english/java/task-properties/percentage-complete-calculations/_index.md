---
title: Percentage Complete Calculations for Tasks in Aspose.Tasks
linktitle: Percentage Complete Calculations for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 25
url: /java/task-properties/percentage-complete-calculations/
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
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;


public class PercentageCompleteCalculations {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "Software Development.mpp");

        TaskCollection alTasks = project.getRootTask().getChildren();
        for (Task tsk : alTasks) {
            System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
            System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
            System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
        }
    }
}





```

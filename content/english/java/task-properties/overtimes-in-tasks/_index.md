---
title: Overtimes in Tasks with Aspose.Tasks
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 23
url: /java/task-properties/overtimes-in-tasks/
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
import com.aspose.tasks.Tsk;


public class OvertimesInTasks {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //Create new project
        Project project = new Project(dataDir + "TaskOvertimes.mpp");

        for (Task tsk : project.getRootTask().getChildren()) {
            System.out.println(tsk.get(Tsk.OVERTIME_COST));
            System.out.println(tsk.get(Tsk.OVERTIME_WORK).toString());
            System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
            System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
            System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());

            // set percent complete
            tsk.set(Tsk.PERCENT_COMPLETE, 100);
        }
    }
}





```

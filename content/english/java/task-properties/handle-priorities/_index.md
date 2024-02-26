---
title: Handle Task Priorities in Aspose.Tasks
linktitle: Handle Task Priorities in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 17
url: /java/task-properties/handle-priorities/
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



import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;


public class HandlePriorities {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "project.xml");

        // Create a ChildTasksCollector instance
        ChildTasksCollector collector = new ChildTasksCollector();

        // Collect all the tasks from RootTask using TaskUtils
        TaskUtils.apply(project.getRootTask(), collector, 0);

        // Handling Priorities:
        // Parse through all the collected tasks
        for (Task tsk : collector.getTasks()) {
            System.out.println(tsk.get(Tsk.PRIORITY).toString());
        }
    }
}





```

---
title: Manage Predecessor and Successor Tasks in Aspose.Tasks
linktitle: Manage Predecessor and Successor Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 15
url: /java/task-links/predecessor-successor-tasks/
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



import com.aspose.tasks.*;


public class PredecessorSuccessorTasks {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "project.mpp");
        TaskLinkCollection allinks = project.getTaskLinks();
        for (TaskLink tsklnk : allinks) {
            System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
            System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
        }
    }
}





```

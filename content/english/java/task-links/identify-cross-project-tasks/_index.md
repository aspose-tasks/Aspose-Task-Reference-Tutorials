---
title: Identify Cross-Project Tasks in Aspose.Tasks
linktitle: Identify Cross-Project Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 14
url: /java/task-links/identify-cross-project-tasks/
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


public class IdentifyCrossProjectTasks {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project externalProject = new Project(dataDir + "External.mpp");

        Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
        //ID of the task in the external project
        System.out.println(externalTask.get(Tsk.ID).toString());
        //ID of the task in the original project
        System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
    }
}





```

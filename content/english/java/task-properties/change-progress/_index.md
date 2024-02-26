---
title: Change Progress of Task in Aspose.Tasks
linktitle: Change Progress of Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 12
url: /java/task-properties/change-progress/
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


public class ChangeProgressOfTask {
    public static void main(String[] args) {
        Project project = new Project();
        //System.out.println(project.getCalculationMode());

        Task task = project.getRootTask().getChildren().add("Task");
        //task.set(Tsk.DURATION, project.getDuration(2));
        task.set(Tsk.PERCENT_COMPLETE, percent(50));
        System.out.println(task.get(Tsk.PERCENT_COMPLETE));
    }

    static int percent(int p) { return p; }
}





```

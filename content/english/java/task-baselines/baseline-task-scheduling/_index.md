---
title: Baseline Task Scheduling in Aspose.Tasks
linktitle: Baseline Task Scheduling in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 10
url: /java/task-baselines/baseline-task-scheduling/
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



import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;

public class BaselineTaskScheduling {
    public static void main(String[] args) {
        Project project = new Project();
        // Creating TaskBaseline:
        Task task = project.getRootTask().getChildren().add("Task");
        project.setBaseline(BaselineType.Baseline);

        TaskBaseline baseline = task.getBaselines().get(0);
        System.out.println(baseline.getDuration().toString());
        System.out.println("Baseline Start: " + baseline.getStart());
        System.out.println("Baseline Finish: " + baseline.getFinish());
    }
}





```

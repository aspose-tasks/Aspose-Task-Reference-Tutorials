---
title: Creating a Task Baseline in Aspose.Tasks
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/task-baselines/create-task-baseline/
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


import java.util.ArrayList;
import java.util.List;

public class CreatingATaskBaseline {
    public static void main(String[] args) {
        Project project = new Project();

        // Creating TaskBaseline:
        Task task = project.getRootTask().getChildren().add("Task");
        // set baseline for specified tasks
        List<Task> myList = new ArrayList<Task>();
        project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
        // or set baseline for the entire project
        project.setBaseline(BaselineType.Baseline);
    }
}





```

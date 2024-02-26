---
title: Create Tasks in Aspose.Tasks
linktitle: Create Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 13
url: /java/task-properties/create-tasks/
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


public class CreateTasks {
    public static void main(String[] args) {
        Project project = new Project();
        Task task = project.getRootTask().getChildren().add("Summary1");
        Task subtask = task.getChildren().add("Subtask1");
    }
}





```

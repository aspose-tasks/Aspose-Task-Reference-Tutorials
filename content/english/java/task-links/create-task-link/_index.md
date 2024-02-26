---
title: Create Task Link in Aspose.Tasks
linktitle: Create Task Link in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/task-links/create-task-link/
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


public class CreateTaskLink {
    public static void main(String[] args) {
        Project project = new Project();
        Task pred = project.getRootTask().getChildren().add("Task 1");
        Task succ = project.getRootTask().getChildren().add("Task 2");
        TaskLink link = project.getTaskLinks().add(pred, succ);

        // Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```

---
title: Create Resource Assignments in Aspose.Tasks
linktitle: Create Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 14
url: /java/resource-assignments/create-resource-assignments/
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
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;


public class CreateResourceAssignments {
    public static void main(String[] args) {
        Project project = new Project();

        Task task = project.getRootTask().getChildren().add("Task");

        Resource rsc = project.getResources().add("Rsc");

        ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
    }
}





```

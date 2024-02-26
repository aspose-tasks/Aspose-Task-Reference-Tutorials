---
title: Calculate Critical Path in Aspose.Tasks Projects
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 10
url: /java/project-management/critical-path/
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


public class CriticalPath {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "New project 2013.mpp");
        project.setCalculationMode(CalculationMode.Automatic);

        Task subtask1 = project.getRootTask().getChildren().add("1");
        Task subtask2 = project.getRootTask().getChildren().add("2");
        Task subtask3 = project.getRootTask().getChildren().add("3");

        project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);

        //Display the critical path now
        for (Task task : project.getCriticalPath()) {
            System.out.println(task.get(Tsk.NAME));
        }

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```

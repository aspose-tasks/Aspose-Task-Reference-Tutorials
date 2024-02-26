---
title: Handle Task Writing Exceptions during Printing in Aspose.Tasks
linktitle: Handle Task Writing Exceptions during Printing in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 23
url: /java/project-management/print-task-exceptions/
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
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TasksWritingException;


public class PrintTaskWritingExceptions {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project prj = new Project(dataDir + "project5.mpp");

        try {
            prj.save(dataDir + "project.mpp", SaveFileFormat.Mpp);
        } catch (TasksWritingException ex) {
            System.out.println(ex.getLogText());
        }
    }
}





```

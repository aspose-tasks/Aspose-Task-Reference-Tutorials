---
title: Update MPP File in Aspose.Tasks
linktitle: Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 19
url: /java/project-management/update-mpp/
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
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;


import java.util.Calendar;

public class MppFileUpdate {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //Read an existing project
        Project project = new Project(dataDir + "SampleMSP2010.mpp");

        //create a new task
        Task task = project.getRootTask().getChildren().add("Task1");
        //set start date
        java.util.Calendar cal = java.util.Calendar.getInstance();

        cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
        task.set(Tsk.START, cal.getTime());

        cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
        task.set(Tsk.FINISH, cal.getTime());

        //Save the project as MPP project file
        project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```
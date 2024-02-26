---
title: Task Duration in Different Units with Aspose.Tasks
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 32
url: /java/task-properties/task-duration-different-units/
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
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;


public class TaskDurationInDifferentUnits {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        // Read MS Project template file
        String fileName = dataDir + "project.xml";

        //Read the input file as Project
        Project project = new Project(fileName);

        //Get a task to calculate its duration in different formats
        Task task = project.getRootTask().getChildren().getById(1);

        //Get the duration in Minutes
        double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
        //Get the duration in Days
        double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
        //Get the duration in Hours
        double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
        //Get the duration in Weeks
        double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
        //Get the duration in Months
        double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
    }
}





```

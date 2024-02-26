---
title: Split Task Finish Date in Aspose.Tasks
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 28
url: /java/task-properties/split-task-finish-date/
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

public class SplitTaskFinishDate {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //Read project
        String projectName = dataDir + "SplitTask.mpp";
        Project project = new Project(projectName);

        //Find a split task
        Task splitTask = project.getRootTask().getChildren().getByUid(1);

        //Find the project calendar
        Calendar calendar = project.get(Prj.CALENDAR);

        //Calculate task's finish date with different durations
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 16 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 16d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 24 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 24d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 28 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 28d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 32 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 32d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 46 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 46d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 61 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 61d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 75 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 75d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 80 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 80d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 120 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 120d));
        System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 150 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 150d));
    }
}





```

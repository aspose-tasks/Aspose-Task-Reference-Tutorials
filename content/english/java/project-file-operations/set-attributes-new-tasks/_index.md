---
title: Set Attributes for New Tasks in Aspose.Tasks
linktitle: Set Attributes for New Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 21
url: /java/project-file-operations/set-attributes-new-tasks/
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



import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;


public class SetAttributesForNewTasks {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //create a prject instance
        Project prj = new Project();

        //set new task property
        prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);

        //save the project in XML format
        prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);

        //Display result of conversion.
        System.out.println("Project file generated Successfully");
    }
}





```

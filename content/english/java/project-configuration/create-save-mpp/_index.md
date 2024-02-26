---
title: Create and Save Empty Project in MPP Format with Aspose.Tasks
linktitle: Create and Save Empty Project in MPP Format with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 12
url: /java/project-configuration/create-save-mpp/
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



import java.io.IOException;

import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;


public class CreateEmptyProjectSaveMpp {
    public static void main(String[] args) {
        // ExStart: CreateEmptyProjectSaveMPP
        // For complete examples and data files, please go to https://github.com/aspose-tasks/Aspose.Tasks-for-Java
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //Create a project instance
        Project newProject = new Project();

        newProject.save(dataDir + "project1.mpp", SaveFileFormat.Mpp);

        //Display result of conversion.
        System.out.println("Project file generated Successfully");
        // ExEnd: CreateEmptyProjectSaveMPP
    }
}

```

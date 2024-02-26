---
title: Create Empty Project File in Aspose.Tasks
linktitle: Create Empty Project File in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/project-configuration/create-empty-project-file/
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


public class CreateEmptyProjectFile {
    public static void main(String[] args) {
        // ExStart: CreateEmptyProjectFile
        // For complete examples and data files, please go to https://github.com/aspose-tasks/Aspose.Tasks-for-Java
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        // Create a project instance
        Project newProject = new Project();

        newProject.save(dataDir + "project1.xml", SaveFileFormat.Xml);

        //Display result of conversion.
        System.out.println("Project file generated Successfully");
        // ExEnd: CreateEmptyProjectFile
    }
}





```

---
title: Create and Save Empty Project to Stream in Aspose.Tasks
linktitle: Create and Save Empty Project to Stream in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 13
url: /java/project-configuration/create-save-stream/
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


import java.io.IOException;
import java.io.OutputStream;
import java.nio.file.Files;
import java.nio.file.Paths;

public class CreateEmptyProjectSaveStream {
    public static void main(String[] args) throws IOException {
        // ExStart: CreateEmptyProjectSaveStream
        // For complete examples and data files, please go to https://github.com/aspose-tasks/Aspose.Tasks-for-Java
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //Create a project instance
        Project newProject = new Project();

        // Create a file stream
        OutputStream projectStream = Files.newOutputStream(Paths.get(dataDir + "EmptyProjectSaveStream_out.xml"));

        newProject.save(projectStream, SaveFileFormat.Xml);

        //Display result of conversion.
        System.out.println("Project file generated Successfully");
        // ExEnd: CreateEmptyProjectSaveStream

    }
}

```

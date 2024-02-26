---
title: Read Project Files in Aspose.Tasks
linktitle: Read Project Files in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 15
url: /java/project-data-reading/read-project-files/
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
import com.aspose.tasks.ProjectFileInfo;


import java.io.FileInputStream;

public class ReadProjectFiles {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        CheckIfProjectIsPasswordProtected(dataDir);
        ReadProjectAsTemplate(dataDir);
        ReadProjectFileFromStream(dataDir);
    }

    public static void CheckIfProjectIsPasswordProtected(String dataDir) {
        //ExStart: CheckIfProjectIsPasswordProtected
        ProjectFileInfo info = Project.getProjectFileInfo(dataDir + "project.mpp");
        System.out.println("Is file password protected? " + info.isPasswordProtected());
        //ExEnd: CheckIfProjectIsPasswordProtected
    }

    public static void ReadProjectAsTemplate(String dataDir) {
        // ExStart: ReadProjectAsTemplate
        // For complete examples and data files, please go to https://github.com/aspose-tasks/Aspose.Tasks-for-Java
        // Read existing project template file
        Project project = new Project(dataDir + "project.mpp");
        System.out.println("Name : " + project.get(Prj.NAME));
        // ExEnd: ReadProjectAsTemplate
    }

    public static void ReadProjectFileFromStream(String dataDir) {
        // ExStart: ReadProjectFiles
        // For complete examples and data files, please go to https://github.com/aspose-tasks/Aspose.Tasks-for-Java
        try {
            FileInputStream prjStream = new FileInputStream(dataDir + "project.mpp");
            Project existingProject = new Project(prjStream);
            prjStream.close();

            System.out.println("Calendar : " + existingProject.get(Prj.NAME));
        } catch (Exception ex) {
            System.out.println(ex.getMessage());
        }
        // ExEnd: ReadProjectFiles
        // Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```

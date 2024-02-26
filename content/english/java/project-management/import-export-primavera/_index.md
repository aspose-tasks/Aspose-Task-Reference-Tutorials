---
title: Import and Export Data to Primavera in Aspose.Tasks
linktitle: Import and Export Data to Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 18
url: /java/project-management/import-export-primavera/
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



import com.aspose.tasks.FileFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectFileInfo;
import com.aspose.tasks.SaveFileFormat;


import java.io.IOException;

public class ImportExportDataToPrimavera {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        importingprimaveraxml(dataDir);

        exportingprimaveraxml(dataDir);

        exportingprimaveraxer(dataDir);

        exportingprimaverampx(dataDir);
        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }

    public static void importingprimaveraxml(String dataDir) {
        Project project = new Project(dataDir + "primavera1.xml");

        //read the project structure
        ProjectFileInfo info = Project.getProjectFileInfo(dataDir + "primavera1.xml");
        System.out.println(FileFormat.getName(FileFormat.class, info.getProjectFileFormat()));
    }

    public static void exportingprimaveraxml(String dataDir) {
        Project project = new Project(dataDir + "project.mpp");

        project.save(dataDir + "saved.xml", SaveFileFormat.PrimaveraP6Xml);
    }

    public static void exportingprimaveraxer(String dataDir) {
        Project project = new Project(dataDir + "project.mpp");

        project.save(dataDir + "saved.xer", SaveFileFormat.PrimaveraXer);
    }

    public static void exportingprimaverampx(String dataDir) {
        Project project = new Project(dataDir + "project.mpp");

        project.save(dataDir + "saved.mpx", SaveFileFormat.Mpx);
    }
}





```

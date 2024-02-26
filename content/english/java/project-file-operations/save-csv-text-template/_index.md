---
title: Save As CSV, Text, and Template in Aspose.Tasks
linktitle: Save As CSV, Text, and Template in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 16
url: /java/project-file-operations/save-csv-text-template/
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

import com.aspose.tasks.*;


public class SaveAsCsvTextAndTemplate {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";
        SavingProjectAsCsv(dataDir);

        SavingProjectAsText(dataDir);

        SavingProjectAsTemplate(dataDir);

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }

    public static void SavingProjectAsCsv(String dataDir) {
        Project project = new Project(dataDir + "project5.mpp");
        project.save(dataDir + "project5.csv", SaveFileFormat.Csv);
    }

    public static void SavingProjectAsText(String dataDir) {
        Project project = new Project(dataDir + "project5.mpp");
        project.save(dataDir + "project5.txt", SaveFileFormat.Txt);
    }

    public static void SavingProjectAsTemplate(String dataDir) {
        String projectName = dataDir + "Blank2010.mpp"; // any mpp file (here 2010 format used)
        Project project = new Project(projectName);
        ProjectFileInfo projectFileInfo = Project.getProjectFileInfo(dataDir + "Blank2010.mpp");

        if (FileFormat.MPP14 == projectFileInfo.getProjectFileFormat()) {
            System.out.println("Project file format is ok");
        }
        SaveTemplateOptions options = new SaveTemplateOptions();
        options.setRemoveActualValues(true);
        options.setRemoveBaselineValues(true);

        String templateName = "result.mpt";
        project.saveAsTemplate(templateName);

        ProjectFileInfo templateFileInfo = Project.getProjectFileInfo(templateName);
        if (FileFormat.MPT14 == templateFileInfo.getProjectFileFormat()) {
            System.out.println("Template FileFormat is ok");
        }
    }
}





```

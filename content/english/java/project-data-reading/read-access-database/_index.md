---
title: Reading Project Data from Microsoft Access Database with Aspose.Tasks
linktitle: Reading Project Data from Microsoft Access Database with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/project-data-reading/read-access-database/
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



import com.aspose.tasks.MpdSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;


import java.io.IOException;

public class ReadingProjectDataFromMicrosoftAccessDatabase {
    // ExStart: ReadingProjectDataFromMicrosoftAccessDatabase
    public static void main(String[] args) {
        // For complete examples and data files, please go to https://github.com/aspose-tasks/Aspose.Tasks-for-Java
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        MpdSettings settings = new MpdSettings(getConnectionString(), 1);
        Project project = new Project(settings);
        project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
    }

    private static String getConnectionString() {
        return "jdbc:odbc:DRIVER=Microsoft Access Driver (*.mdb, *.accdb);DBQ=" + "mpdFile.mpd";
    }
    // ExEnd: ReadingProjectDataFromMicrosoftAccessDatabase
}

```

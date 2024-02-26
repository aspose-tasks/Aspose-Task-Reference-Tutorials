---
title: Read Table Data from File in Aspose.Tasks
linktitle: Read Table Data from File in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 17
url: /java/project-data-reading/read-table-data/
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
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;


public class ReadTableDataFromFile {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "Project2003.mpp");

        Table t1 = project.getTables().toList().get(0);
        System.out.println("Table Fields Count: " + t1.getTableFields().size());
        System.out.println();

        for (TableField f : t1.getTableFields()) {
            System.out.println("Field width: " + f.getWidth());
            System.out.println("Field Title: " + f.getTitle());
            System.out.println("Field Title Alignment: " + f.getAlignTitle());
            System.out.println("Field Align Data: " + f.getAlignData());
            System.out.println();
        }
    }
}





```

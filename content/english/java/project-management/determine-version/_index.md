---
title: Determine Project Version with Aspose.Tasks
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 12
url: /java/project-management/determine-version/
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


public class DetermineProjectVersion {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "input.xml");

        //Display project version property
        System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
        System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```

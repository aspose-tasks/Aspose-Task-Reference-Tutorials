---
title: Read Password-Protected Files in Aspose.Tasks
linktitle: Read Password-Protected Files in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 14
url: /java/project-data-reading/read-password-protected/
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


public class ReadPasswordProtectedFiles {
    public static void main(String[] args) {
        // ExStart: ReadPasswordProtectedFiles
        // For complete examples and data files, please go to https://github.com/aspose-tasks/Aspose.Tasks-for-Java
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project prj = new Project(dataDir + "PasswordProtected.mpp", "pass");

        //Display result of conversion.
        System.out.println("Process completed Successfully");
        // ExEnd: ReadPasswordProtectedFiles
    }
}





```

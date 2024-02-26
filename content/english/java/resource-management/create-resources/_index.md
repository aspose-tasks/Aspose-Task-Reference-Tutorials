---
title: Create Resources in Aspose.Tasks
linktitle: Create Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 10
url: /java/resource-management/create-resources/
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
import com.aspose.tasks.Resource;

public class CreateResources {
    public static void main(String[] args) {
        Project project = new Project();
        Resource rsc = project.getResources().add("Rsc");
    }
}





```

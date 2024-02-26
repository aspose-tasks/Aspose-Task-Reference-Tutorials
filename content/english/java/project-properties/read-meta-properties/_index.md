---
title: Read Meta Properties in Aspose.Tasks Projects
linktitle: Read Meta Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 10
url: /java/project-properties/read-meta-properties/
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



import com.aspose.tasks.BuiltInProjectProperty;
import com.aspose.tasks.CustomProjectProperty;
import com.aspose.tasks.Project;

import com.aspose.tasks.examples.Tasks.ActualProperties;

public class ReadMetaProperties {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";
        // ExStart: ReadMetaProperties
        // Create a project reader instance
        Project project = new Project(dataDir + "project.mpp");

        // Custom properties are available through the typed collection:
        for (CustomProjectProperty property : project.getCustomProps()) {
            System.out.println(property.getType());
            System.out.println(property.getName());
            System.out.println(property.getValue());
        }

        // Built-in properties are available directly:
        System.out.println(project.getBuiltInProps().getAuthor());
        System.out.println(project.getBuiltInProps().getTitle());

        // or as an item of built-in property collection:
        for (BuiltInProjectProperty property : project.getBuiltInProps()) {
            System.out.println(property.getName());
            System.out.println(property.getValue());
        }
        // ExEnd:ReadMetaProperties
    }
}
```

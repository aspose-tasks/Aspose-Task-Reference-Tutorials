---
title: Handle Extended Attributes in Aspose.Tasks Projects
linktitle: Handle Extended Attributes in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 13
url: /java/project-management/extended-attributes/
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



import java.util.Date;

import com.aspose.tasks.*;


public class ExtendedAttributes {
    public static void main(String[] args) {
        // ExStart: ExtendedAttributes
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project prj = new Project(dataDir + "project5.mpp");
        ExtendedAttributeDefinitionCollection eads = prj.getExtendedAttributes();

        // Create extended attribute definition
        ExtendedAttributeDefinition attributeDefinition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
        prj.getExtendedAttributes().add(attributeDefinition);

        eads.add(attributeDefinition);

        // Get zero index task
        Task tsk = prj.getRootTask().getChildren().getById(1);
        ExtendedAttributeCollection eas = tsk.getExtendedAttributes();

        // Add extended attribute
        ExtendedAttribute ea = attributeDefinition.createExtendedAttribute();

        Date date = new Date();
        ea.setDateValue(date);

        eas.add(ea);

        prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);

        // Display result of conversion.
        System.out.println("Process completed Successfully");
        // ExEnd: ExtendedAttributes
    }
}

```

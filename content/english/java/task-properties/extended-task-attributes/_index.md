---
title: Extended Task Attributes in Aspose.Tasks
linktitle: Extended Task Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 16
url: /java/task-properties/extended-task-attributes/
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



import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;


public class ExtendedTaskAttributes {
    public static void main(String[] args) {
        // ExStart:ReadTaskExtendedAttributes
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");

        for (Task tsk : project.getRootTask().getChildren()) {
            for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
                System.out.println(ea.getFieldId());
                System.out.println(ea.getValueGuid());

                switch (ea.getAttributeDefinition().getCfType()) {
                    case CustomFieldType.Date:
                    case CustomFieldType.Start:
                    case CustomFieldType.Finish:
                        System.out.println(ea.getDateValue());
                        break;

                    case CustomFieldType.Text:
                        System.out.println(ea.getTextValue());
                        break;

                    case CustomFieldType.Duration:
                        System.out.println(ea.getDurationValue().toString());
                        break;

                    case CustomFieldType.Cost:
                    case CustomFieldType.Number:
                        System.out.println(ea.getNumericValue());
                        break;

                    case CustomFieldType.Flag:
                        System.out.println(ea.getFlagValue());
                        break;
                }
            }
        }
        // ExEnd:ReadTaskExtendedAttributes
    }
}





```
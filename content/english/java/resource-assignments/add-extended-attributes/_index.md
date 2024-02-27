---
title: Add Extended Attributes to Resource Assignments in Aspose.Tasks
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 10
url: /java/resource-assignments/add-extended-attributes/
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
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;


import java.io.IOException;
import java.math.BigDecimal;

public class AddExtendedAttributesToResourceAssignments {
    public static void main(String[] args) {
        AddPlainExtendedAttributeToResourceAssignment();
        AddLookUpExtendedAttributeToResourceAssignment();
    }

    public static void AddPlainExtendedAttributeToResourceAssignment() {
        String dataDir = "Your Data Directory";

        // ExStart: AddPlainExtendedAttributeToResourceAssignment
        Project project = new Project(dataDir + "Blank2010.mpp");

        // Add new task and resource
        Task task1 = project.getRootTask().getChildren().add("Task");
        Resource rsc1 = project.getResources().add("Rsc");

        // Assign the resource desired task
        ResourceAssignment assn = project.getResourceAssignments().add(task1, rsc1);

        ResourceAssignment assignment = project.getResourceAssignments().toList().get(0);

        // Custom attributes which is visible in "Resource Usage" view can be created
        // with ExtendedAttributeDefinition.CreateResourceDefinition method.
        ExtendedAttributeDefinition resCostAttr = ExtendedAttributeDefinition.createResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");

        project.getExtendedAttributes().add(resCostAttr);

        ExtendedAttribute value = resCostAttr.createExtendedAttribute();
        value.setNumericValue(BigDecimal.valueOf(1500));
        assignment.getExtendedAttributes().add(value);

        // Custom attributes which is visible in "Task Usage" view can be created with
        // ExtendedAttributeDefinition.CreateTaskDefinition method
        ExtendedAttributeDefinition resCostAttr2 = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Cost, ExtendedAttributeTask.Cost5, "My cost for task");

        project.getExtendedAttributes().add(resCostAttr2);

        value = resCostAttr2.createExtendedAttribute();
        value.setNumericValue(BigDecimal.valueOf(2300));

        assignment.getExtendedAttributes().add(value);

        project.save(dataDir + "AddExtendedAttributesToResourceAssignment_out.mpp", SaveFileFormat.Mpp);
        // ExEnd: AddPlainExtendedAttributeToResourceAssignment
    }

    public static void AddLookUpExtendedAttributeToResourceAssignment() {
        String dataDir = "Your Data Directory";
        // ExStart: AddLookUpExtendedAttributeToResourceAssignment
        Project project = new Project(dataDir + "Blank2010.mpp");

        ExtendedAttributeDefinition resCostAttr = ExtendedAttributeDefinition.createLookupResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My lookup cost");

        Value value1 = new Value();
        value1.setNumericValue(BigDecimal.valueOf(1500));
        value1.setDescription("Val 1");
        value1.setId(1);
        value1.setVal("1500");

        resCostAttr.addLookupValue(value1);

        Value value2 = new Value();
        value1.setNumericValue(BigDecimal.valueOf(2500));
        value1.setDescription("Val 2");
        value1.setId(2);

        resCostAttr.addLookupValue(value2);

        project.getExtendedAttributes().add(resCostAttr);

        ExtendedAttribute value = resCostAttr.createExtendedAttribute(value1);
        value.setNumericValue(BigDecimal.valueOf(1500));
        project.save(dataDir + "AddExtendedAttributesToRAWithLookUp_out.mpp", SaveFileFormat.Mpp);
        // ExEnd: AddLookUpExtendedAttributeToResourceAssignment
    }
}

```
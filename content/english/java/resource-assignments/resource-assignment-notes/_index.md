---
title: Manage Notes for Resource Assignments in Aspose.Tasks
linktitle: Manage Notes for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 21
url: /java/resource-assignments/resource-assignment-notes/
---

## Complete Source Code
```java


import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;


public class ResourceAssignmentNotes {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project prj = new Project(dataDir + "UpdateResourceAssignment.mpp");

        Task task = prj.getRootTask().getChildren().getById(1);
        Resource rsc = prj.getResources().getById(1);

        // Create resource assignment
        ResourceAssignment assn = prj.getResourceAssignments().add(task, rsc);

        // Set resource assignment notes
        assn.set(Asn.NOTES_TEXT, "Newly added assignment");

        System.out.println("Notes text: " + assn.get(Asn.NOTES_TEXT));
        System.out.println("Notes RTF: " + assn.get(Asn.NOTES_RTF));

        // Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}

```

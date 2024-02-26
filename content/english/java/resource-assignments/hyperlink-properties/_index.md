---
title: Manage Hyperlink Properties for Resource Assignments in Aspose.Tasks
linktitle: Manage Hyperlink Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 16
url: /java/resource-assignments/hyperlink-properties/
---

## Complete Source Code
```java


import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;

import java.util.Calendar;

public class HyperlinkProperties {
    public static void main(String[] args) {
        Project prj = new Project();

        Task task = prj.getRootTask().getChildren().add("Task 1");
        java.util.Calendar cal = java.util.Calendar.getInstance();
        cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
        task.set(Tsk.START, cal.getTime());
        task.set(Tsk.DURATION, prj.getDuration(8));

        Resource resource = prj.getResources().add("Resource 1");

        // Create resource assignment
        ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);

        assignment.set(Asn.HYPERLINK, "Click to visit our site");
        assignment.set(Asn.HYPERLINK_ADDRESS, "https://products.aspose.com");
        assignment.set(Asn.HYPERLINK_SUB_ADDRESS, "/total/net");

        System.out.println("Hyperlink: " + assignment.get(Asn.HYPERLINK));
        System.out.println("Hyperlink Address: " + assignment.get(Asn.HYPERLINK_ADDRESS));
        System.out.println("Hyperlink Sub Address: " + assignment.get(Asn.HYPERLINK_SUB_ADDRESS));

        // Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}

```

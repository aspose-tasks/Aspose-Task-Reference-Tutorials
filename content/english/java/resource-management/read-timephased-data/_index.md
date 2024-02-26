---
title: Read Timephased Data for Resources in Aspose.Tasks
linktitle: Read Timephased Data for Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 15
url: /java/resource-management/read-timephased-data/
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
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;


public class ReadTimephasedData {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        // Read Microsoft Project template file
        String fileName = "ResourceTimephasedData.mpp";

        //Read the input file as Project
        Project project = new Project(dataDir + fileName);

        //Get the Resource by its ID
        Resource resource = project.getResources().getByUid(1);

        // Print Timephased data of ResourceWork
        System.out.println("Timephased data of ResourceWork");
        for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
            System.out.println("Start: " + td.getStart().toString());
            System.out.println(" Work: " + td.getValue());
        }
        // Print Timephased data of ResourceCost
        System.out.println("Timephased data of ResourceCost");
        for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
            System.out.println("Start: " + td.getStart().toString());
            System.out.println(" Cost: " + td.getValue());
        }
    }
}





```

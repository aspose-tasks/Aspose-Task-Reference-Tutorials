---
title: Save As PDF in Aspose.Tasks
linktitle: Save As PDF in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 17
url: /java/project-file-operations/save-as-pdf/
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



import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;


public class SaveAsPdf {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        // Read the input Project file
        Project project = new Project(dataDir + "HomeMovePlan.mpp");

        // Save the Project as PDF
        project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);

        // Fitting contents to cell size
        Project project1 = new Project(dataDir + "project6.mpp");
        SaveOptions o = new PdfSaveOptions();

        // Set the row height to fit cell content
        o.setFitContent(true);
        o.setTimescale(Timescale.Months);
        o.setPresentationFormat(PresentationFormat.TaskUsage);
        project1.save("result_months.pdf", o);

        // Set the LegendOnEachPage property to false to hide legends
        o.setLegendOnEachPage(false);

        project1.save(dataDir + "result_months_WithoutLegend.pdf", o);

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```

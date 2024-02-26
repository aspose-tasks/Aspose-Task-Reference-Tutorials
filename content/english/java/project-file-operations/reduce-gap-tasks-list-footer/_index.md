---
title: Reducing Gap Between Tasks List and Footer in Aspose.Tasks
linktitle: Reducing Gap Between Tasks List and Footer in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 10
url: /java/project-file-operations/reduce-gap-tasks-list-footer/
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



import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;


import java.io.IOException;

public class ReducingGapBetweenTasksListAndFooter {
    public static void main(String[] args) {
        //ExStart: ReducingGapBetweenTasksListAndFooter
        String dataDir = "Your Data Directory";

        //Read the MPP file.
        Project project = new Project(dataDir + "HomeMovePlan.mpp");

        //Use ReduceFooterGap property to reduce the gap between list of tasks and Footer
        ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
        imageSaveOptions.setReduceFooterGap(true);
        imageSaveOptions.setRenderToSinglePage(false);
        imageSaveOptions.setPageSize(PageSize.A0);
        imageSaveOptions.setTimescale(Timescale.Days);
        project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);

        PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
        pdfSaveOptions.setReduceFooterGap(true);
        pdfSaveOptions.setSaveToSeparateFiles(true);
        pdfSaveOptions.setPageSize(PageSize.A0);
        pdfSaveOptions.setTimescale(Timescale.Days);
        project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);

        HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
        htmlSaveOptions.setReduceFooterGap(true); // set to true
        htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
        htmlSaveOptions.setIncludeProjectNameInTitle(false);
        htmlSaveOptions.setPageSize(PageSize.A0);
        htmlSaveOptions.setTimescale(Timescale.Days);
        project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
        //ExEnd: ReducingGapBetweenTasksListAndFooter
    }
}

```

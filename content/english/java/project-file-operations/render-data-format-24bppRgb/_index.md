---
title: Render Data with Format 24bppRgb in Aspose.Tasks
linktitle: Render Data with Format 24bppRgb in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/project-file-operations/render-data-format-24bppRgb/
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



import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PixelFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;


public class RenderDataWithFormate24bppRgb {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "project.mpp");
        ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Tiff);
        options.setHorizontalResolution(72);
        options.setVerticalResolution(72);
        options.setPixelFormat(PixelFormat.Format24bppRgb);
        project.save(dataDir + "resFile.tif", options);
    }
}





```

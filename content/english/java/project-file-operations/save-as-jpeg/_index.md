---
title: Save Project As JPEG in Aspose.Tasks
linktitle: Save Project As JPEG in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 20
url: /java/project-file-operations/save-as-jpeg/
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
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;


import java.io.IOException;

public class SaveProjectAsJpeg {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //ExStart: SaveProjectAsJPEG
        Project project = new Project(dataDir + "HomeMovePlan.mpp");

        // in order to manipulate JPEG quality one can use ImageSaveOptions.JpegQuality property.
        // The allowed value range is 0..100.
        ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
        options.setJpegQuality(50);

        project.save(dataDir + "image_out.jpeg", options);
        //ExEnd: SaveProjectAsJPEG
    }
}

```

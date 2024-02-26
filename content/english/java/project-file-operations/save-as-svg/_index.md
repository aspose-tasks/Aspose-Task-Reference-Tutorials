---
title: Save As SVG in Aspose.Tasks
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 18
url: /java/project-file-operations/save-as-svg/
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



import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;


import java.io.IOException;

public class SaveAsSvg {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        SavingProjectDataAsSVG(dataDir);

        UsingSvgOptions(dataDir);

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }

    public static void SavingProjectDataAsSVG(String dataDir) {
        // Read the input Project file
        Project project = new Project(dataDir + "HomeMovePlan.mpp");
        // Save the Project as SVG
        project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
    }

    public static void UsingSvgOptions(String dataDir) {
        // Read the input Project file
        Project project = new Project(dataDir + "HomeMovePlan.mpp");

        SaveOptions opt = new SvgOptions();
        opt.setFitContent(true);
        opt.setTimescale(Timescale.ThirdsOfMonths);
        project.save(dataDir + "FileName5.svg", opt);
    }
}





```

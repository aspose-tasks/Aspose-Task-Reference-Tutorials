---
title: Set Currency Properties in Aspose.Tasks Projects
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/currency-properties/set-properties/
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



import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;


public class SetCurrencyProperties {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //Create a project instance
        Project project = new Project();

        //Set currency properties
        project.set(Prj.CURRENCY_CODE, "AUD");
        project.set(Prj.CURRENCY_DIGITS, 2);
        project.set(Prj.CURRENCY_SYMBOL, "$");
        project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);

        //Save the project as XML project file
        project.save(dataDir + "project.xml", SaveFileFormat.Xml);

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```

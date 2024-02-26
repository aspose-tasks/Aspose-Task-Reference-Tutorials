---
title: Read Currency Properties in Aspose.Tasks Projects
linktitle: Read Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 10
url: /java/currency-properties/read-properties/
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



import com.aspose.tasks.*;


public class ReadCurrencyProperties {
    public static void main(String[] args) {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        //Create a project reader instance
        Project project = new Project(dataDir + "project.mpp");

        //Display currency properties
        System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
        System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
        System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
        System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }
}





```

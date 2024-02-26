---
title: Handle Currency Digits with Aspose.Tasks
linktitle: Handle Currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
description: 
type: docs
weight: 11
url: /java/currency/currency-digits/
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



import java.io.IOException;

import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;


public class CurrencyDigits {
    public static void main(String[] args) {
        settingCurrencyDigits();

        gettingCurrencyDigits();

        //Display result of conversion.
        System.out.println("Process completed Successfully");
    }

    public static void settingCurrencyDigits() {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project();
        project.set(Prj.CURRENCY_DIGITS, 2);
        project.save(dataDir + "ProjectCurrDigits.mpp", SaveFileFormat.Mpp);
    }

    public static void gettingCurrencyDigits() {
        // The path to the documents directory.
        String dataDir = "Your Data Directory";

        Project project = new Project(dataDir + "project.mpp");
        System.out.println(project.get(Prj.CURRENCY_DIGITS));
    }
}





```
